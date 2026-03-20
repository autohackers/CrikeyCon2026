# Autohackers @ CrikeyCon 2026
![Autohackers Logo](https://autohackers.org/content/images/2023/05/ah-text-bw.png)
## Tesla Model Y 2024 CAN Bus interface

### FAQ
Why a Tesla?
* Multiple reasons, including:
   * At the time of purchase, there was a high value proposition of this vehicle compared to the available competition (in Australia). This included cost, utility (as a 'Bunnings + dogs' car it beats most) and the fact it is pretty much a 'software defined car' ... which lead us to think "hmm, let's see what we can break."
   * The idea of "hack a Tesla" would seem to appeal to more people than, say, "hack a Ford" or "hack a Hyundai"... and we already have "hack a Porsche" (albeit an older model, not an EV) in the Autohackers stable of vehicles.

Why do you support Tesla?
* Autohackers does not 'support' any car manufacturer. This Tesla was bought before the very public CEO decided to exhibit his facist nature. The vehicle would not have been procured post that point... if any EV manufacturer has an equivalent vehicle they'd like to swap out for our Model Y at next to no cost, please get in touch.

## Porsche 2004 CAN dashboard & RPi
What was the purpose of this dashboard?
* A few years ago we had a Porsche 996 (2004) at CrikeyCon with a RPi + PiCAN hat, wired into the 'drivetrain' CAN bus of the car. The remote dashboard could play back data captured in the vehicle and had a few CTF challenges associated with it. The primary use now is to be able to write CAN packets directly onto the bus to see how the dashboard reacts - "CAN 101" hands on learning, and testing of understanding (i.e. how the various bytes in a packet can be used to display data on devices).
Original conference post https://autohackers.org/content-for-crikeycon8-ctf/

* See the folder 'Porsche996' for example data dumps and code files for injection.

