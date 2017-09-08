# Unscented Kalman Filter Project Code

## Process Modeling 
The unscented Kalman filter (UKF) algorithm requires a function that describes the evolution of states from one time-step to the next. This is typically called the state transition function shown as.
- Non additive process noise: T[k+1] = f (T[k], Q[k])
- Here f(..) is the state transition function, T is the state, Q is the process noise. 

## Sensor Modeling
UKF also needs a function that describes how the model states are related to sensor measurements. 
- Non additive measurement noise: z[k+1] = h (z[k], R[k])
- Here h(..) is the measurement function, z is sensor measurement and R is the measurement noise.

