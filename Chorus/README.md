#[Analysis](../README.md) > Chorus

The chorus effect is responsile for thickening-up the sound of the Juno 60. It takes a single channel from the [High pass filter](../Filter/HPF/README.me) and emits stereo channels.

The module contains 1 triangle-wave LFO, modulating 2 Bucket-Brigade delay-lines (1 for left and 1 for right).  The modulation signal of the right delay-line is inverted so it is effectively 180 degrees out of phase with the left channel.

| Name | Rate | Min delay | Max delay | Outputs | Notes |
| --- | --- | --- | --- | --- | --- |
| Chorus 1 | 0.5 Hz | 0.00166 | 0.00535 | Stereo | Described as "mild chorus" |
| Chorus 2 | 2 Hz | 0.00166 | 0.00535 | Stereo | Described as "deeper richer chorus" |
| Chorus 1 + 2 | 14 Hz | 0.0033 | 0.0037 | Mono | Described as "similar to a Leslie rotary speaker" |

The [Pirkle FX book](../Resources/Book_PirkleFx.md) says that the minumim delay for chorus effects is normally 7ms.  My analysis indicates that the Juno chorus 1 & 2 effects should be classified as "flanger", and that the "1+2" effect is probably better described as a "vibrato".

A discussion on the [KVR forum](http://www.kvraudio.com/forum/viewtopic.php?t=313797&start=15) indicates that a 12dB low-pass filter is used before the signal is sampled into the Bucket-Brigade chips. I was worried that the Bucket-Brigade chips would introduce an large amount of bit-crushing to the effect - but it looks like the chips are effectively sampling at about 70kHz (so should be minor).
