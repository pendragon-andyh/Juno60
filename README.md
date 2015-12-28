#Juno60
##Introduction
This project aims to analyse the sound of Roland's [Juno 60](https://en.wikipedia.org/wiki/Roland_Juno-60) synthesizor with the eventual aim of recreating its distinctive sounds using the [Web Audio API](https://webaudio.github.io/web-audio-api/).

I decomposed the Juno 60 into the following functional areas so that I can analyse each in isolation:
* [DCO](DCO/README.md) -
    [Sawtooth](DCO/Sawtooth/README.md),
    [PWM](DCO/PWM/README.md),
    [Sub oscillator](DCO/Sub/README.md),
    [Noise](DCO/Noise/README.md),
    [Mix down](DCO/Mixdown/README.md)
* [Envelope](Envelope/README.md) -
    [Attack](Envelope/Attack/README.md),
    [Decay](Envelope/Decay/README.md),
    [Release](Envelope/Release/README.md),
    [PWM modulation](Envelope/PWM/README.md),
    [LPF modulation](Envelope/LPF/README.md)
* TBC

##Testing
The test plan is documented [here](TestPlan/README.md). Most of my analysis was carried-out using the brilliant [Sonic Visualiser](http://www.sonicvisualiser.org/) software.

##Resources
I found the following resources helpful for understanding the analogue synths.
* [URLs for Juno 60](Resources/Juno60/README.md)
* [URLs for Juno 106](Resources/Juno106/README.md) - has almost identical sound engine.
* [Books](Resources/Books/README.md)
* [Web Audio API](Resources/WebAudioAPI/README.md)

Any mistakes and misinterpretations are entirely my fault.

##Licensing
Copyright (c) 2015 Andy Harman and Pendragon Software Limited.

Released under the [MIT license](MIT-LICENSE.md). Please feel free to reuse the techniques developed in this project in your own projects.
