# Autohackers @ CrikeyCon 2026
![Autohackers Logo](https://autohackers.org/content/images/2023/05/ah-text-bw.png)
## Tesla Model Y 2024 CAN Bus interface

The objective here was simply to gain access to the main CAN Bus in the vehicle in order to see, and later modify, data on that bus in order to achieve things that the Tesla software may not allow the user to do.

At CrikeyCon, we'll be interfacing using the [EVTV CANdue box](https://store.evtv.me/en-au/products/teslamodel3cankit2) that is using an ESP32 microcontroller with 2x CAN ports. The main reason for using this interface is that it was able to be purchased with the proprietary connectors needed to splice into the Y's CAN bus, which is located in the centre console, from the rear seats.

To interface with the CANdue box, we're running [SavvyCAN](https://www.savvycan.com/) and [SavvyCAN github](https://github.com/collin80/SavvyCAN) for code and look at [SavvyCAN releases](https://github.com/collin80/SavvyCAN/releases/tag/continuous) for a quick binary download for your OS.

SavvyCAN allows us to both view/capture data from the CAN bus and also insert frames back onto the bus. 

### FAQ
Why a Tesla?
* Multiple reasons, including:
   * At the time of purchase, there was a high value proposition of this vehicle compared to the available competition (in Australia). This included cost, utility (as a 'Bunnings + dogs' car it beats most) and the fact it is pretty much a 'software defined car' ... which lead us to think "hmm, let's see what we can break."
   * The idea of "hack a Tesla" would seem to appeal to more people than, say, "hack a Ford" or "hack a Hyundai"... and we already have "hack a Porsche" (albeit an older model, not an EV) in the Autohackers stable of vehicles.

Why do you support Tesla?
* Autohackers does not 'support' any car manufacturer. This Tesla was bought before the very public CEO decided to exhibit his facist nature. The vehicle would not have been procured post that point... if any EV manufacturer has an equivalent vehicle they'd like to swap out for our Model Y at next to no cost, please get in touch.

Safety
* We're serious about safety, especially when it's not just 'me' working on a car directly! To that end, the rear wheel drive vehicle will be up on jack stands (at the rear) just in case a command is accepted that may make the rear wheels turn... can't have a Tesla roaming loose in the CrikeyCon CTF space! (Given the 'summon' feature exists, it is reasonable to assume the safeguards that would normally prevent a car from moving without a driver present are able to be bypassed in software alone, so extra safety measures are in place for this.) There's also chocks at the front wheels, to limit any rolling; even though a 2 ton car is hard to push-start by hand.

## Porsche 2004 CAN dashboard & RPi
What was the purpose of this dashboard?
* A few years ago we had a Porsche 996 (2004) at CrikeyCon with a RPi + PiCAN hat, wired into the 'drivetrain' CAN bus of the car. The remote dashboard could play back data captured in the vehicle and had a few CTF challenges associated with it. The primary use now is to be able to write CAN packets directly onto the bus to see how the dashboard reacts - "CAN 101" hands on learning, and testing of understanding (i.e. how the various bytes in a packet can be used to display data on devices).
Original conference post https://autohackers.org/content-for-crikeycon8-ctf/

* See the folder 'Porsche996' for example data dumps and code files for injection.

