# ROB2A_V23

## Verkefni 1

### Hluti 1

#### Flæðirit: 

![ alt text for screen readers](https://github.com/BirgirBragi/ROB2A_V23/blob/main/Verkefni1/Verkefni%201.drawio.png) 

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

