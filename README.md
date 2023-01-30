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
