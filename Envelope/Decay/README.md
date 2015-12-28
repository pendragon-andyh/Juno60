#[Envelope](../README.md) > Decay

##Duration
The user guide tells us that the duration of the decay segment ranges from 2ms to 12s. The diagrams indicate that the duration at the half-way point of the decay slider is 1 second. However, the supporting text says that positions in the diagrams are not meant to be exactly correct.

###Duration (when sustain-level = 0)
The following values were measured directly from the Juno 60 (with the sustain-level set to 0):

| Slider value | Duration (seconds) |
| - | - |
| 0 | 0.002 |
| 2.5 | 0.096 |
| 5 | 0.984 |
| 7.5 | 4.449 |
| 10 | 19.783 |

Note that the slider values are approximate (they were manually set).
The figures clearly show that the relationship between the slider-position and the resulting duration is logarithmic.

The closest match that I could model was with the following formula:
> Duration = 0.002 + (EXP(slider \* 0.4) - 1) / (EXP(10 \* 0.4) - 1) \* slider \* 0.1 \* 17.46

Where:
0.002 = the minimum duration;
17.46 = the maximum duration;
0.4 = my fudge factor.

###Duration (when sustain-level = 5)
The following values were measured directly with the sustain-level set to 5:

| Slider value | Duration (seconds) |
| - | - |
| 0 | 0.001 |
| 5 | 1.253 |
| 10 | 17.11 |

This was a bit of a surprise for me. The xxxx book says that the delay duration on analog synths normally reduces when the sustain-level is increases.

##Slope
The decay rate for analog synths is normally curved because the represent the charge-rate of a capacitor.

The following values were measured when the slider was set to 10 (and the sustain-level is 0):

| Position (seconds) | Normalized-level |
| - | - | - |
| 0.0 | 1.000 |
| 1.0 | 0.764 |
| 2.0 | 0.616 |
| 3.0 | 0.511 |
| 4.0 | 0.423 |
| 5.0 | 0.359 |
| 6.0 | 0.296 |
| 7.0 | 0.250 |
| 8.0 | 0.205 |
| 9.0 | 0.173 |
| 10.0 | 0.148 |
| 11.0 | 0.116 |
| 12.0 | 0.106 |
| 13.0 | 0.081 |
| 14.0 | 0.067 |
| 15.0 | 0.049 |
| 16.0 | 0.046 |
| 17.0 | 0.025 |
| 18.0 | 0.021 |
| 19.0 | 0.014 |
| 20.0 | 0.000 |

The xxxx book gives us the following generic formula for calcuation the level of the attack phase over time:
> Level = (EXP(-4.95 \* x \* RC)

Where:
* x = values between 0.0 and 1.0 (based on how far through the decay-phase we are);
* RC = a constant that is based on the resistor \* capacitor on-which the envelope is based.

The closest match that I could model was:
> Level = SustainLevel + ((1-SustainLevel) \* EXP(-3.5 \* x)) - EXP(-3.5)

Where:
* x = values between 0.0 and 1.0 (based on how far through the decay-phase we are);
* SustainLevel = The level of the sustain slider (0.0 to 1.0).
* -3.5 = my fudge factor.
