# Lokaverkefni

### Hönnun/Teikning

![](https://github.com/BirgirBragi/ROB2A_V23/blob/main/robo%20lokaverkefni%20teikning.jpg)

### Lýsing

Þetta verkefni felst í því að robot er settur í miðjuna (eða bara einhvers staðar) inn í hring merktan á gólfinu með svörtu tape-i. Markmið robotsins er síðan að fjarlægja alla kubba sem settir eru inn í hringin. Robotinn á að snúast í hringi á meðan enginn kubbur er innan tape-sins, ultrasonic sensor er notaður til þess að skynja það. Um leið og ultrasonic sensorinn tekur eftir kubb, fer drivetrainið í áttina að kubbnum. Síðann er claw notað til þess að taka upp kubb og setja fyrir utan tape (sem line sensorar skynja).

### Vélbúnaður

- 2 Drivetrain Motorar
- 2 Motorar fyrir Claw og Arm
- Line Sensor
- UltraSonic Sensor

### Flæðirit

![](https://github.com/BirgirBragi/ROB2A_V23/blob/main/Lokaverk.jpg)

### Kóði

```C++

#include "vex.h"

using namespace vex;

int printTask(){
    Brain.Screen.clearScreen();
    Brain.Screen.setCursor(1,1);
    Brain.Screen.print(ultrasonicSensor.distance(vex::distanceUnits::in));
    wait(0.3,sec);
    return 0;
}

int mainTask() {

  const int SPIN_SPEED = 10;
  const int CLAW_SPEED_OPEN_CLOSE = 10;
  const int CLAW_SPEED_RAISE_LOWER = 10;
  const int ULTRASONIC_DISTANCE_THRESHOLD = 10;

  while (true) {
    if(ultrasonicSensor.distance(vex::distanceUnits::in) <= 15){
      wait(0.5, sec);
      while (ultrasonicSensor.distance(vex::distanceUnits::in) > ULTRASONIC_DISTANCE_THRESHOLD) {
        Drivetrain.drive(forward);
        vex::task::sleep(20);
      }

      Drivetrain.stop();
      Drivetrain.drive(reverse);

      wait(0.3,sec);

      Drivetrain.stop();

      wait(0.3,sec);

      Drivetrain.stop();

      clawMotorRaiseLower.spin(reverse, CLAW_SPEED_RAISE_LOWER, vex::velocityUnits::pct);

      wait(3,sec);

      clawMotorOpenClose.spin(forward, CLAW_SPEED_OPEN_CLOSE, vex::velocityUnits::pct);

      wait(3,sec);

      Drivetrain.drive(forward);
      
      wait(2, sec);

      Drivetrain.stop();

      clawMotorRaiseLower.spin(reverse, CLAW_SPEED_RAISE_LOWER, vex::velocityUnits::pct);

      wait(5,sec);
      
      clawMotorOpenClose.spin(reverse, CLAW_SPEED_OPEN_CLOSE, vex::velocityUnits::pct);

      wait(3,sec);

      clawMotorRaiseLower.spin(forward, CLAW_SPEED_RAISE_LOWER, vex::velocityUnits::pct);

      wait(5,sec);

      Drivetrain.setDriveVelocity(10,percent);
      Drivetrain.drive(forward);
      while (lineSensor.reflectivity() >= 30) {
        vex::task::sleep(20);
      }
      Drivetrain.stop();

      wait(3,sec);

      clawMotorRaiseLower.spin(reverse, CLAW_SPEED_RAISE_LOWER, vex::velocityUnits::pct);

      wait(5,sec);

      clawMotorOpenClose.spin(forward, CLAW_SPEED_OPEN_CLOSE, vex::velocityUnits::pct);

      wait(3,sec);

      clawMotorOpenClose.stop();
      clawMotorRaiseLower.stop();

      Drivetrain.drive(reverse);

      wait(6,sec);

      Drivetrain.stop();

      wait(3,sec);

      clawMotorOpenClose.spin(reverse, CLAW_SPEED_OPEN_CLOSE, vex::velocityUnits::pct);

      wait(3,sec);
      clawMotorRaiseLower.spinToPosition(110,degrees);
      wait(3,sec);
    }
    if (lineSensor.reflectivity() > 30) {
      // Spin the robot
      Drivetrain.setTurnVelocity(SPIN_SPEED, vex::velocityUnits::pct);
      Drivetrain.turn(right);
    }

      
    }
}

int main(){
  vexcodeInit();
  clawMotorRaiseLower.spinToPosition(110,degrees);
  wait(1,sec);
  vex::task t(mainTask);
  vex::task v(printTask);
}
```

### Myndband

linkur: [https://youtu.be/UzKiSvZUkqY](https://youtu.be/UzKiSvZUkqY)
