# Term 2 - Project #4 PID Controller 

## Compilation

- The code successfully compiles using cmake .. && make
- The program can be executed by running the file "./pid" and using the term 2 simulator to view the car driving autonomously around the track

## Implementation

- This project was completed with help from the classroom material as well as the project overview video

## Reflection

### Effects of each of the P, I and D components in my implementation

#### Proportional Control (Kp = -0.3)
- This component is used to control how much the wheel is turned based on how far away we are from the reference trajectory using the cross track error.
- This may result in the car pointing in an incorrect direction when it reaches the correct trajectory resulting in oscillation. 
- The higher the value the more the stronger the steering input. On one extreme, the car would end up going in circles while on the other the steering correction was not enough to keep the car on track
- This value needs to be balanced by the D component

#### Differential Control (Kd = -8.0)
- This component is used to control how much the car overshoots once the target trajectory is met
- It acts as a damper to the P component by controlling the oscillation as the CTE error reduces
- A high value of D acts as a stronger counter steer while a lower value is less aggressive


#### Integral Control (Ki = 0.0)
- The integral component is used to correct for a bias such as an alignment error, cross-winds, road surface imperfections
- In this particular test track, introducing even a small amount of I value caused the car to go off-track.
- This means there is little to no bias for this particular test case scenario so this was left as 0.


#### Throttle
- I was able to achieve a maximum speed of 45 mph without having the car go off track
- Although a lower speed allowed for a much smoother drive (with minimal oscillations), this speed was chosen as it was the fastest the car could go around the track while staying within the prescribed area


## Simulation
- The car successfully went around the track without leaving the driveable portion of the track surface or rolling over the chicane/ledges
