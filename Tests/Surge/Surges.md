# EMC Guide from a beginner. Surges

Surges are key tests to prove the immunity to high power pulses.
They are usually compared to lightning or more generic atmospheric events but they can also be caused due to high power equipment failure.
Everything that is connected to main power lines is subject to this kind of events, and they are most prominent in industrial settings.

Depending on the environment and the required standard, surge testing may be done only on power ports but can also be required by signal ports.
This can be required since in industrial or generic high power environments  signal lines coupling with power can be substantial, so the equipment must be able to manage these kinds of events.
Fortunately, since surge events are sporadic and relatively short, the standards may prescribe different acceptance criteria.

I work for industrial distribution and circuit breakers, and in my case I need to guarantee the protection functionality of the object during the whole transient, but I don't need to guarantee accessory functionalities during the event itself, only before and after the transient. the object may signal some temporary visual/data malfunction, but it must immediately recover without damages and in an automatic way, without operator intervention.
This is done since we are positioned electrically very close to the distribution lines and phisically we are positioned into the "power center" of the installation. Surge events are a threat and we must guarantee protection functionality in any moment, but accessory functionalities like monitoring and measures are not priority.

## Pulse Shape
Surge waveforms are experimentally measured during well... surge events.
after that they are standardized in the 61000-4-5 or equivalent.

- 8/20us is usually associated with power equipment faults.
- 1.2/50us is usually associated with lighning strikes
- 10/1000us is associatet with long powerlines surges

all of these follow the same scheme of a combination exponential wave.