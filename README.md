# SelfDrivCar_PID_Controller

## P controller

With only P controller, Simulated car oscillates much and overshoots the target (i.e middle of the road). As p-controller steers the car in proportion to the cross track error, after adjusting itself towards the mid of the road, it doesnt changes the steering value(till code gets the next steering value) and so continues the path and often overshoots the target(i.e. mid of the road). Though car simulates, its movement is marginally stable. But car doesnt converges to the mid of the road.
When I tried with the larger value of the Kp, it oscillates faster than the low value of the Kp.


## D Controller.

D Controller moves the car towards the target considering the difference between the current and previous cross track error. So contineously changes the steering values in proportion to the difference in CTE. So car steers somoothly towards the mid of the car. Thus eliminates the overshoot which is the disadvantage of the p-controller.


## I-controller

I controller tries to eliminate the bias due to the steering drift. I used Ki=1 for the project. It looks simulator car has some steer drift.

## Controller Parameter Tunning:

I tried to use twiddle code, but no idea on how to stop and restart the simulator from the code. So tuned the parameters manually.

I have started with p-controller parameter(Kp). Initially used Kp=0.1,Kd=0 and Ki=0,but car was oscillating much. Then changed the kp=0.05. This slows down the oscillations, but failed on the steep curve when the car overshoots on the curve and goes off-track.Even tried with Kp=0.2, which gives more oscillations than the Kp=0.1. So finalised on the Kp=0.05.

For the next step, I have tried Kd of 0.01(Kp=0.05, Kd=0.01, Ki=0). Result is earlier start of the oscillations. Kd = 0.05 gave worst results. So reduced Kd to 0.005 which gave better results with smoother and smaller oscillations. After reducing Kd to 0.0001, car was behaving well and stable for long travelling distance till it gets off-track on the steep curve. 

Next step is to decide on the i-controller parameter Ki. To satrt with I have used Ki=1 and worked really well. Car continued the travell for whole lap without going off-track. It looks simulator car has some drift which is eliminated by using the i-controller. Tried with Ki values of 5,2.5 and 0.5, but have not got better results than the Ki=1

Thus Kp=0.05 Kd=0.0001 and Ki=1 are the final values for the pid controller.

## Below are the links to the Car Simulation Video
### With P Controller Only
[https://youtu.be/0ww0mYcTMUo](https://youtu.be/0ww0mYcTMUo)
### With PID Controllers
[https://youtu.be/9NYxCFGommM](https://youtu.be/9NYxCFGommM)



