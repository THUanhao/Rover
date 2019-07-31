## First
Target: (1) Used for uncertain information about some dynamic system
        (2) Make an educated guess about what the system is going to do next

## Second
Kalman Filter is ideal for systems which are continuously changing(Don't need to keep any history other than the previous state)

## Third
Structure: (1) Xk is a state function whihc is just a list of numbers about the undelying configuration of system
           (2) Kalman Filter assumes that both variables are random and Gaussian distributed. Each variable has a mean value                u, which is the center of the random distribution and a variance.
           (3) Correlation is captured by something called a covariance matrix. Each element of the matrix is the degree of                  correlation between the ith state variable and the j state variable
           
### Example
Describling the problem with matrices. Call best estimate Xk (the mean, elsewhere named u) and covariance matirx Pk
Xk = [Position
      Velocity]
Pk = [∑pp ∑pv
      ∑vp ∑vv]                ⑴
      
Current state(at time k-1) and predict the next state k. Represent this prediction step with a matrix Fk
Pk = Pk-1 + ∆t*Vk-1
Vk = Vk-1                     ⑵
Xk = [1   ∆t
     0    1] * Xk-1 = Fk*Xk-1 ⑶

Then we need to update the covariance matrix. If multiply every point in a distribution by a matrix A, then the covariance matrix ∑ would be change to 
Cov(x) = ∑
Cov(Ax) = A∑A′         (A′ = inverse of matrix A)    ⑷

Combining (4) with equation (3)
#### Xk = Fk*Xk-1
#### Pk = FkPk-1Fk′        ⑸

## Fourth
