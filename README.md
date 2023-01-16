# ROB2A_V23

## Verkefni 1

### Hluti 1

#### Flæðirit: 

![](https://github.com/BirgirBragi/ROB2A_V23/blob/main/Verkefni1/Verkefni%201.drawio.png) 

#### Kóði:

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
 
Myndband: [https://youtube.com/shorts/2IStZavei58](https://youtube.com/shorts/2IStZavei58).

### Hluti 2

#### Flæðirit:

![](https://github.com/BirgirBragi/ROB2A_V23/blob/main/Verkefni1/Verkefni%201%20hluti%202.drawio.png)

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

Myndband: [https://youtube.com/shorts/gSnHiCNbB_4?feature=share](https://youtube.com/shorts/gSnHiCNbB_4?feature=share).


## Verkefni 2

### Hluti 1

#### Flæðirit

![](https://github.com/BirgirBragi/ROB2A_V23/blob/main/Verkefni%202/Verkefni%202.jpg)

#### Kóði

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

Myndband: [https://youtu.be/bRrz6u8fqKY](https://youtu.be/bRrz6u8fqKY)

### Hluti 2

#### Flæðirit

#### Kóði

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

Myndband: [https://youtube.com/shorts/dTDOvD2s9gM?feature=share](https://youtube.com/shorts/dTDOvD2s9gM?feature=share)
