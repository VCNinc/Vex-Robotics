/*
    Team: 6546
    Competition: Vex Nothing but Net [2015]
    Authors: Aaron Cruz, Vivek Nair
*/

/*
		Motor Reference
		---------------
		Port 2: Back Left Drive Motor
		Port 3: Back Right Drive Motor
		Port 4: Front Left Drive Motor
		Port 5: Front Right Drive Motor
		Port 6: Left Shooter Motor
		Port 7: Right Shooter Motor
		Port 8: Intake Motor
		Port 9: Conveyor / Lift Motor
*/

#pragma platform(VEX)

//Competition Control and Duration Settings
#pragma competitionControl(Competition)
#pragma autonomousDuration(20) //20
#pragma userControlDuration(120)

#include "Vex_Competition_Includes.c"

void pre_auton()
{
  bStopTasksBetweenModes = true;
}

task autonomous()
{
  // Enable Shooter
	motor[port6] = 75;
	motor[port7] = -75;
	
	// Wait for 3 Seconds
	wait(3);
	
	// Enable Conveyor / Lift and Intake
	motor[port8] = -160;
	motor[port9] = -160;
}

task usercontrol()
{
	UserControlCodePlaceholderForTesting();

	while (true)
	{
		// Tank Drive Left Side
		motor[port2] = vexRT[Ch3];
		motor[port4] = vexRT[Ch3];

		// Tank Drive Right Side
		motor[port3] = vexRT[Ch2] * -1;
		motor[port5] = vexRT[Ch2] * -1;

		// Shooter
		if (vexRT[Btn5U]){
			motor[port6] = 75;
			motor[port7] = -75;
		} else if(vexRT[Btn5D]) {
			motor[port6] = 50;
			motor[port7] = -50;
		} else {
	  	motor[port6] = 0;
			motor[port7] = 0;
		}

		// Intake
		if (vexRT[Btn6U]){
			motor[port8] = -160;
			motor[port9] = -160;
		} else if (vexRT[Btn6D]) {
			motor[port8] = 160;
			motor[port9] = 160;
		} else {
			motor[port8] = 0;
			motor[port9] = 0;
		}
	}
}
