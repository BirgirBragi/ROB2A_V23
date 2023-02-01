# ROB2A_V23

## Verkefni 1

### Hluti 1

#### Flæðirit: 

![](https://github.com/BirgirBragi/ROB2A_V23/blob/main/Verkefni1/Verkefni%201.drawio.png) 

#### Kóði:
```C++
     include "vex.h"

    using namespace vex;

    int main() {
      // Initializing Robot Configuration. DO NOT REMOVE!
      vexcodeInit();

      int dist = 500;
      while (dist != 2500){
        Drivetrain.driveFor(forward,dist,mm);
        Drivetrain.driveFor(reverse,dist,mm);
        dist += 500;
      }
    }
 ```
Myndband: [https://youtube.com/shorts/2IStZavei58](https://youtube.com/shorts/2IStZavei58).

### Hluti 2

#### Flæðirit:

![](https://github.com/BirgirBragi/ROB2A_V23/blob/main/Verkefni1/Verkefni%201%20hluti%202.drawio.png)
```C++

    #include "vex.h"

    using namespace vex;

    int main() {
    // Initializing Robot Configuration. DO NOT REMOVE!
      vexcodeInit();

      int dist = 500;
      Drivetrain.driveFor(forward,dist,mm);
      Drivetrain.turnFor(right, 90, degrees);

      Drivetrain.driveFor(forward,dist,mm);
      Drivetrain.turnFor(left, 90, degrees);

      Drivetrain.driveFor(forward,dist,mm);
      Drivetrain.turnFor(left, 90, degrees);

      Drivetrain.driveFor(forward,dist,mm);
      Drivetrain.turnFor(right, 90, degrees);

      Drivetrain.driveFor(forward,dist,mm);
      Drivetrain.turnFor(right, 90, degrees);

      Drivetrain.driveFor(forward,dist,mm);
      Drivetrain.turnFor(left, 90, degrees);

      Drivetrain.driveFor(forward,dist,mm);
      Drivetrain.turnFor(right, 90, degrees);

      Drivetrain.driveFor(forward,dist,mm);
      Drivetrain.turnFor(right, 90, degrees);

      Drivetrain.driveFor(forward,dist,mm);
      Drivetrain.turnFor(left, 90, degrees);

      Drivetrain.driveFor(forward,dist,mm);
      Drivetrain.turnFor(right, 90, degrees);

      Drivetrain.driveFor(forward,dist,mm);
      Drivetrain.turnFor(right, 90, degrees);

      Drivetrain.driveFor(forward,dist,mm);
      Drivetrain.turnFor(left, 90, degrees);

      Drivetrain.driveFor(forward,dist,mm);
      Drivetrain.turnFor(left, 90, degrees);

      Drivetrain.driveFor(forward,dist,mm);
      Drivetrain.turnFor(right, 90, degrees);

      Drivetrain.driveFor(forward,dist,mm);
    }
```

Myndband: [https://youtube.com/shorts/gSnHiCNbB_4?feature=share](https://youtube.com/shorts/gSnHiCNbB_4?feature=share).


## Verkefni 2

### Hluti 1

#### Flæðirit

![](https://github.com/BirgirBragi/ROB2A_V23/blob/main/Verkefni%202/Verkefni%202.jpg)

#### Kóði
```C++
    #include "vex.h"

    using namespace vex;

    // Declare Contoller event callbacks.
    void whenControllerL1Pressed() {
      // Lift the ArmMotor.
      ArmMotor.spin(forward);
      // Wait until L1 is released.
      waitUntil(!Controller1.ButtonL1.pressing());
      // Stop the motor
      ArmMotor.stop();
    }
    void whenControllerL2Pressed() {
      // Lower the ArmMotor.
      ArmMotor.spin(reverse);
      // Wait until L2 is released.
      waitUntil(!Controller1.ButtonL2.pressing());
      // Stop the motor
      ArmMotor.stop();

    }
    void whenControllerR1Pressed() {
      // Open the ClawMotor.
      ClawMotor.spin(reverse);
      // Wait until R1 is released.
      waitUntil(!Controller1.ButtonR1.pressing());
      // Stop the motor
      ClawMotor.stop();

    }
    void whenControllerR2Pressed() {
      // Close the ClawMotor.
      ClawMotor.spin(forward);
      // Wait until R2 is released.
      waitUntil(!Controller1.ButtonR2.pressing());
      // Stop the motor
      ClawMotor.stop();
    }

    int main() {
      // Initializing Robot Configuration. DO NOT REMOVE!
      vexcodeInit();

      // Initialize the Contoller Events
      Controller1.ButtonL1.pressed(whenControllerL1Pressed);
      Controller1.ButtonL2.pressed(whenControllerL2Pressed);
      Controller1.ButtonR1.pressed(whenControllerR1Pressed);
      Controller1.ButtonR2.pressed(whenControllerR2Pressed);

      // Set the brake mode and velocity of the ArmMotor and ClawMotor
      ClawMotor.setStopping(hold);
      ArmMotor.setStopping(hold);

      ClawMotor.setVelocity(30, percent);
      ClawMotor.setVelocity(60, percent);

      // Use tank drive to control the robot.
      while (true) {
        LeftMotor.setVelocity(Controller1.Axis3.position(), percent);
        RightMotor.setVelocity(Controller1.Axis2.position(), percent);
        LeftMotor.spin(forward);
        RightMotor.spin(forward);
    
        wait(25, msec);
      }
  
    }
```

Myndband: [https://youtu.be/bRrz6u8fqKY](https://youtu.be/bRrz6u8fqKY)

### Hluti 2

#### Flæðirit

![](https://github.com/BirgirBragi/ROB2A_V23/blob/main/Untitled%20Diagram.drawio.png)

#### Kóði
```C++
     #include "vex.h"

     using namespace vex;

     void stop() {
       task::stopAll();
       //Drivetrain.stop(hold);
     }



     int mainTask() {
       // Initializing Robot Configuration. DO NOT REMOVE!
       Controller1.ButtonB.pressed(stop);{
         int dist = 500;
         Drivetrain.driveFor(forward,dist,mm);
         Drivetrain.turnFor(right, 90, degrees);

         Drivetrain.driveFor(forward,dist,mm);
         Drivetrain.turnFor(left, 90, degrees);

         Drivetrain.driveFor(forward,dist,mm);
         Drivetrain.turnFor(left, 90, degrees);

         Drivetrain.driveFor(forward,dist,mm);
         Drivetrain.turnFor(right, 90, degrees);

         Drivetrain.driveFor(forward,dist,mm);
         Drivetrain.turnFor(right, 90, degrees);

         Drivetrain.driveFor(forward,dist,mm);
         Drivetrain.turnFor(left, 90, degrees);

         Drivetrain.driveFor(forward,dist,mm);
         Drivetrain.turnFor(right, 90, degrees);

         Drivetrain.driveFor(forward,dist,mm);
         Drivetrain.turnFor(right, 90, degrees);

         Drivetrain.driveFor(forward,dist,mm);
         Drivetrain.turnFor(left, 90, degrees);

         Drivetrain.driveFor(forward,dist,mm);
         Drivetrain.turnFor(right, 90, degrees);

         Drivetrain.driveFor(forward,dist,mm);
         Drivetrain.turnFor(right, 90, degrees);

         Drivetrain.driveFor(forward,dist,mm);
         Drivetrain.turnFor(left, 90, degrees);

         Drivetrain.driveFor(forward,dist,mm);
         Drivetrain.turnFor(left, 90, degrees);

         Drivetrain.driveFor(forward,dist,mm);
         Drivetrain.turnFor(right, 90, degrees);

         Drivetrain.driveFor(forward,dist,mm);

       }
       return 0;
     }

     int main(){
       vexcodeInit();
       vex::task t(mainTask);
     }
```

Myndband: [https://youtube.com/shorts/dTDOvD2s9gM?feature=share](https://youtube.com/shorts/dTDOvD2s9gM?feature=share)

## Verkefni 3

### Hluti 1

#### Flæðirit:

![](https://github.com/BirgirBragi/ROB2A_V23/blob/main/Verkefni%203/Untitled%20Diagram.jpg)

#### Kóði
```C++
     #include "vex.h"

     using namespace vex;
     double startTimeA = Brain.timer(vex::timeUnits (sec));

     void stop() {
        task::stopAll();
        Drivetrain.stop();
      }

     int speedTask(){
       double vel = 0.0;
       //int startTimi = Brain.timer(vex::timeUnits (sec));
       int currTimi;
       float metrar = 0;
       float velocityTimesFive = 0;
       int counter = 0;
       while(true){
          vel = Drivetrain.velocity(rpm);
          float rps = vel/60;
          float omega = 2 * 3.14159265359 * rps;
          float V = omega * 0.05;
          Brain.Screen.print("%.2f", V);
          Brain.Screen.print(" m/s ");
          //Brain.Screen.print(startTimi);
          Brain.Screen.print(" ");
          currTimi = Brain.timer(vex::timeUnits (sec));
          //if(currTimi - startTimi == 1){
          if(counter<5){
             velocityTimesFive += V;
             counter++;
           }
           else{
             counter = 0;
             metrar += velocityTimesFive/5;
             velocityTimesFive = 0;
           }
          Brain.Screen.print("%.2f",metrar);
          Brain.Screen.print(" m ");
          wait(200,msec);
          Brain.Screen.setCursor(1, 1);
          Brain.Screen.clearScreen();
       }
       return 0;
     }

     int mainTask() {
       // Initializing Robot Configuration. DO NOT REMOVE!
       // Wait 1 second before driving forward.
       //wait(1, seconds);
       //vex::task t(drivingTask);

       // The robot will stop driving when the Range Finder is less than 300 mm away
       // from an object.
         BumperE.pressed(stop);

         while(BumperE.pressing()!= true){  
         if (LightF.brightness() > 0 && LightF.brightness() < 50) {
           Drivetrain.stop();
         }
         else{
           //Brain.Screen.print("%.2f", RangeFinderG.distance(mm));
           //wait(50, msec);
           //Brain.Screen.setCursor(1, 1);
           //Brain.Screen.clearScreen();
           //wait(5, msec);
           if(RangeFinderG.distance(mm) > 300){
             Drivetrain.drive(forward);
           }
           else{
             Drivetrain.turnFor(right,90,degrees);
             wait(500, msec);
           }
         }
         }

         // Brain.Screen.print("%.2f", RangeFinderG.distance(mm));
         // wait(200, msec);
         // Brain.Screen.setCursor(1, 1);
         // Brain.Screen.clearScreen();
         // wait(5, msec);
         return 0;
       }

     int main(){
       vexcodeInit();
       wait(1,sec);
       vex::task t(mainTask);
       vex::task v(speedTask);
     }
```

Myndband: [https://youtu.be/tr4o4p80N7E](https://youtu.be/tr4o4p80N7E)



## Verkefni 4

#### Flæðirit

![](https://github.com/BirgirBragi/ROB2A_V23/blob/main/Verkefni%204/Untitled%20Diagram.drawio%20(1).png)

#### Kóði
```C++
#include "vex.h"

using namespace vex;

void stop() {
  task::stopAll();
  LeftMotor.stop();
  RightMotor.stop();
}

float threshold;

int printTask(){
  threshold = 30;
  while (true){
  if (LineTrackerB.reflectivity() > threshold) {
    Brain.Screen.print("Middle");
  }
  else if (LineTrackerC.reflectivity() > threshold) {
    Brain.Screen.print("Left");
  }
  else if (LineTrackerA.reflectivity() > threshold) {
    Brain.Screen.print("Right");
  }
  wait(5,msec);
  Brain.Screen.setCursor(1, 1);
  Brain.Screen.clearScreen();
  }
  return 0;
}

int mainTask() {
  // Initializing Robot Configuration. DO NOT REMOVE!
  BumperE.pressed(stop);
  threshold = 30;
  while (true) {
    // If the reflectivity is greater than the threshold it will move the LeftMotor forward
    if (LineTrackerB.reflectivity() > threshold) {
      LeftMotor.spin(forward);
      RightMotor.spin(forward);
      // Brain.Screen.print("Middle");
      // wait(5, msec);
      // Brain.Screen.setCursor(1, 1);
      // Brain.Screen.clearScreen();
      //RightMotor.stop();
    }
    if(LineTrackerC.reflectivity() > threshold){
      RightMotor.spin(forward);
      LeftMotor.stop();
      // Brain.Screen.print("Left");
      // wait(5, msec);
      // Brain.Screen.setCursor(1, 1);
      // Brain.Screen.clearScreen();
    }
    if(LineTrackerA.reflectivity() > threshold){
      LeftMotor.spin(forward);
      RightMotor.stop();
      // Brain.Screen.print("Right");
      // wait(5, msec);
      // Brain.Screen.setCursor(1, 1);
      // Brain.Screen.clearScreen();
    }
    wait(5, msec);
    // Brain.Screen.setCursor(1, 1);
    // Brain.Screen.clearScreen();
  }
}

int main(){
  vexcodeInit();
  vex::task t(mainTask);
  vex::task p(printTask);
}

```

Myndband: [https://youtu.be/_dlASHCSRMg](https://youtu.be/_dlASHCSRMg)

## Verkefni 5

#### Kóði

```C++
#include "vex.h"

using namespace vex;

// Function to run when the emergency stop button is pressed
void onEStopPressed() {
  RoboticArm1.emergencyStop();
}

// Task function to constantly display the arm position and sensor values on the brain screen
int positionSensorDisplay() {
  while (true) {
    Brain.Screen.clearScreen();

    // Display the X position on row 1
    Brain.Screen.setCursor(1, 1);
    Brain.Screen.print("Arm X: %0.3f", RoboticArm1.getAxisPosition(xaxis));

    // Display the Y position on row 2
    Brain.Screen.newLine();
    Brain.Screen.print("Arm Y: %0.3f", RoboticArm1.getAxisPosition(yaxis));

    // Display the Z position on row 3
    Brain.Screen.newLine();
    Brain.Screen.print("Arm Z: %0.3f", RoboticArm1.getAxisPosition(zaxis));

    // Display if a disk is detected on row 4
    Brain.Screen.newLine();
    Brain.Screen.print("Disk Detect: %s", Optical6.isNearObject() ? "TRUE" : "FALSE");

    // Display the color of the disk if an object is found on row 5
    Brain.Screen.newLine();
    Brain.Screen.print("R: %s", Optical6.color() == red ? "TRUE" : "FALSE");
    Brain.Screen.print(" / B: %s", Optical6.color() == blue ? "TRUE" : "FALSE");
    Brain.Screen.print(" / G: %s", Optical6.color() == green ? "TRUE" : "FALSE");

    // Display the percentage of light reflected back from the Load Sensor on row 6
    Brain.Screen.newLine();
    Brain.Screen.print("Load: %3d", Load.reflectivity());

    // Display the percentage of light reflected back from the Pickup Sensor on row 7
    Brain.Screen.newLine();
    Brain.Screen.print("Pickup: %3d", Pickup.reflectivity());

    // Display the percentage of light reflected back from the Exit Sensor on row 8
    Brain.Screen.newLine();
    Brain.Screen.print("Exit: %3d", Exit.reflectivity());
    wait(0.2, seconds);
  }
  return 0;
}

// sort a red disc
void onRedDetected() {
  // Insert code here for sorting the red discs
  EntryMotor.spin(forward);
  wait(2,sec);
  EntryMotor.stop();
  TransportMotor.spin(forward);
  waitUntil(Load.reflectivity()>10);
  DiverterMotor.spinToPosition(90,degrees);
  ExitMotor.spin(forward);
  waitUntil(Exit.reflectivity()>10);
  TransportMotor.stop();
  ExitMotor.stop();
}

// sort a green disc
void onGreenDetected() {
    EntryMotor.spin(forward);
    wait(2,sec);
    EntryMotor.stop();
    TransportMotor.spin(forward);
    waitUntil(Load.reflectivity()>10);
    DiverterMotor.spinToPosition(0,degrees);
    waitUntil(Pickup.reflectivity()>10);
    TransportMotor.stop();
    wait(1,sec);
    RoboticArm1.moveToPositionJoint(4.384,-0.029,3.2);
    wait(20,sec);
    RoboticArm1.moveToPositionJoint(4.229,6.270, 2.760);
    wait(1,sec);
    RoboticArm1.moveToPositionJoint(4.229,6.270, 2.460);
    Magnet7.pickup();
    wait(1,sec);
    RoboticArm1.moveToPositionJoint(8.891,4.111,2.842);
    wait(1,sec);
    Magnet7.drop();
}

// sort a blue disc
void onBlueDetected() {
  // Insert code here for sorting the blue discs
    EntryMotor.spin(forward);
    wait(2,sec);
    EntryMotor.stop();
    TransportMotor.spin(forward);
    waitUntil(Load.reflectivity()>10);
    DiverterMotor.spinToPosition(0,degrees);
    waitUntil(Pickup.reflectivity()>10);
    //DiverterMotor.stop();
    TransportMotor.stop();
    wait(1,sec);
    RoboticArm1.moveToPositionJoint(4.384,-0.029,3.2);
    wait(20,sec);
    RoboticArm1.moveToPositionJoint(4.229,6.270, 2.760);
    wait(1,sec);
    RoboticArm1.moveToPositionJoint(4.229,6.270, 2.660);
    Magnet7.pickup();
    wait(1,sec);
    RoboticArm1.moveToPositionJoint(8.891,4.111,2.842);
    wait(1,sec);
    Magnet7.drop();
}

int main() {
  // Initializing Robot Configuration. DO NOT REMOVE!
  vexcodeInit();
  
    // register emergency stop event handler
  EStop.pressed(onEStopPressed);

  // short wait to make sure the emergency stop event is fully registered
  wait(15, msec);

  // initial device setup
  RoboticArm1.setMasteringValues(1781,2267,1975,502);
  RoboticArm1.setToolTipOffset(-0.7, 0.0, -1.0);
  Magnet7.setPower(100);
  Optical6.setLight(ledState::on);
  Optical6.setLightPower(100, percent);
  EntryMotor.setVelocity(70, percent);
  TransportMotor.setVelocity(15, percent);
  ExitMotor.setVelocity(50, percent);
  DiverterMotor.setVelocity(30, percent);
  Brain.Screen.setFont(mono30);

  // start the position and sensor value display task
  vex::task positionSensorDisplayTask(positionSensorDisplay);

  // actual logic for sorting discs by color
  while (true) {
    
    waitUntil(Optical6.isNearObject());
    if (Optical6.color() == red) {
      onRedDetected();
    }
    else if (Optical6.color() == blue)
    {
      onBlueDetected();
    }
    else if (Optical6.color() == green)
    {
      onGreenDetected();
    }
    wait(5, msec);
  }
}
```

Myndband: [https://youtu.be/9rEECJ_KkkU](https://youtu.be/9rEECJ_KkkU)
