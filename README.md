# Unscented Kalman Filter Model

The UKF does not need to linearize non-linear functions; instead, the UKF takes representative points (Sigma Points) from a Gaussian distribution. These points will be plugged into the non-linear equations in order to make estimate.

## Following is therory behind key models need to define UKF.

## Process Model
The unscented Kalman filter (UKF) algorithm requires a function that describes the evolution of states from one time-step to the next. This is typically called the state transition function shown as.
- Non additive process noise: T[k+1] = f (T[k], Q[k])
- Here f(..) is the state transition function, T is the state, Q is the process noise. 

## Sensor Model
UKF also needs a function that describes how the model states are related to sensor measurements. 
- Non additive measurement noise: z[k+1] = h (z[k], R[k])
- Here h(..) is the measurement function, z is sensor measurement and R is the measurement noise.

## Choosing Sigma Points
It can be difficult to transform whole state distribution through nonlinear function but it’s easy to transform individual points of state space through nonlinear function. Sigma points are chosen at mean state and standard deviation of every state dimension. Sigma point serves representative of whole distribution. Once we choose sigma points we can pass it through nonlinear function ‘f ’ and then they will come out in predictive state space called transformed sigma points. Mean and covariance of transformed sigma points gives useful approximation of real predicted distribution. In short sigma points give normal distribution of state space after passing it through nonlinear function.

**Following print screen is result of my unscented filter model. px, py, vx, and vy RMSE comes well below the values [.09, .10, .40, .30] listed in project requirement.**

![alt text](https://oelk4a-bn1305.files.1drv.com/y4mEbuSf5yO-XXvHM-mZzUVTtYMbfP_UaQIQG83YPApUwbAj4qOk1cBcMUHWqCaSRG8YRR0y6RPB8v6jqFsk_yOsxjlTaoQdfxx4TYjkY2l-LOBuz4ThBMBCcAdUTsYejpIsQKiZgw2rcYbUFTcnXIDniYEGsGUakipfq4FkHR97Uijf9Efj19LBnz7OqMnT_nlq8z8JQ1JfIMGjiWa3KQXHw?width=1140&height=747&cropmode=none)

