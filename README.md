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
 
Myndband: (https://youtube.com/shorts/2IStZavei58)[https://youtube.com/shorts/2IStZavei58]

### Hluti 2

#### Flæðirit:

![](https://github.com/BirgirBragi/ROB2A_V23/blob/main/Verkefni1/Verkefni%201%20hluti%202.drawio.png)
