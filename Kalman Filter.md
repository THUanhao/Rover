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
Xk = [
position  
   velocity
]  
(2x2 Matrix)Pk = [∑pp ∑pv  
∑vp ∑vv]                ⑴  
      
Current state(at time k-1) and predict the next state k. Represent this prediction step with a matrix Fk  
Pk = Pk-1 + ∆t*Vk-1  
Vk = Vk-1                     ⑵  
(2x2 Matrix)Xk = [1   ∆t  
0    1] * Xk-1 = Fk*Xk-1 ⑶  

Then we need to update the covariance matrix. If multiply every point in a distribution by a matrix A, then the covariance matrix ∑ would be change to  
Cov(x) = ∑  
Cov(Ax) = A∑A′         (A′ = inverse of matrix A)    ⑷  

Combining (4) with equation (3)  
#### Xk = Fk*Xk-1  
#### Pk = FkPk-1Fk′        ⑸  

## Fourth
#### External Influence (Outside thing would be affect the system)
Following the upper example: woth an acceleration a
Pk = Pk-1 + ∆t*Vk-1 + ½a∆t²
Vk = Vk-1 + at
In matrix form: 
Xk = FkXk-1 + [ ½∆t² \\ ∆t] * a
Xk = FkXk-1 + Bk Uk            ⑹
Bk is calld the control matrix and Uk is the control vector

#### External Uncertainty (Something we aren't keeping track)
Each point in Xk-1 is moved to somewhere inside a Gaussian Blob with covariance Qk (Unctracked influences as noise with covariance Qk)
This produces a new Gaussian blob with a different covariance
*Xk = FkXk-1 + BkUk
Pk = FkXk-1Fk' + Qk      (7)
The new Best estimate is a prediction made from previous best estimate, plus a correction for known external influences  
The new uncertainty is predicted from the old uncertainty with same additional uncertainty from the enviroment  

## Fifth
#### Refining the estimate with measurements
1. Each sensors tell us something indirect about the state. In other words, the sensors operate on a state and produce a set of readings  
2. Hk is the value which will change the state value to a type of value that sensors could reading.

Distribution of sensor readings
Uexpected = Hk*Xk
∑expected = HkPkHk'          (8)
Sensor noise covariance Rk  
The distribution has a mean equal to the reading we obeserved which we will call ∑k  
Two Gaussian blobs: One surrounding the mean of our transformed prediction and one surrounding the actual sensor reading we got  

## Sixth
#### Combining Gaussians
![image](https://github.com/wzezhong/Rover/blob/master/images/WechatIMG4.jpeg)
![image](https://github.com/wzezhong/Rover/blob/master/images/WechatIMG5.jpeg)

