#[Analysis](../../Analysis) > [Envelope](../Envelope) > Attack

##Duration
The user guide tells us that the duration of the attack segment ranges from 1ms to 3s. The diagrams indicate that the duration at the half-way point of the attack slider is 1 second. However, the supporting text says that positions in the diagrams are not meant to be exactly correct.

The following values were measured directly from the Juno 60:

| Slider value | Duration (seconds) |
| - | - |
| 0 | 0.001 |
| 2.5 | 0.03 |
| 5 | 0.24 |
| 7.5 | 0.65 |
| 10 | 3.25 |

Note that the slider values are approximate (they were manually set).
The figures clearly show that the relationship between the slider-position and the resulting duration is logarithmic.

The closest match that I could model was with the following formula:
> Duration = 0.001 + (EXP(slider \* 0.5) - 1) / (EXP(10 \* 0.5) - 1) \* 3.25

Where:
0.001 = the minimum duration;
3.25 = the maximum duration;
0.5 = my fudge factor.

##Slope
The attack rate for analog synths are normally slightly curved because the represent the charge-rate of a capacitor.

The following values were measured when the slider was set to 10:

| Duration (seconds) | Level |
| - | - |
| 0.0 | 0.000 |
| 0.5 | 0.224 |
| 1.0 | 0.410 |
| 1.5 | 0.580 |
| 2.0 | 0.716 |
| 2.5 | 0.847 |
| 3.0 | 0.956 |
| 3.25 | 1.000 |

The xxxx book gives us the following generic formula for calcuation the level of the attack phase over time:
> Level = (1 - EXP(-1.5 \* x) / 0.77

The closest match that I could model was:
> Level = (1-EXP(-1 \* x)) / 0.632

Where:
x = values between 0.0 and 1.0 (based on how far through the attack-duration we are);
0.632 = my fudge factor.
