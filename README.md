#Juno60
##Introduction
This project aims to analyse the sound of Roland's [Juno 60](https://en.wikipedia.org/wiki/Roland_Juno-60) synthesizor with the eventual aim of recreating its distinctive sounds using the [Web Audio API](https://webaudio.github.io/web-audio-api/).

I decomposed the Juno 60 into the following functional areas so that I can analyse each in isolation:
* [DCO](DCO/) -
    [Sawtooth](DCO/Sawtooth/),
    [PWM](DCO/PWM/),
    [Sub oscillator](DCO/Sub/),
    [Noise](DCO/Noise/),
    [Mix down](DCO/Mixdown/)
* [Envelope](Envelope/) -
    [Attack](Envelope/Attack/),
    [Decay](Envelope/Decay/),
    [Release](Envelope/Release/),
    [PWM modulation](Envelope/PWM/),
    [LPF modulation](Envelope/LPF/)
* [Filter](Filter/) -
    [VCF](Filter/VCF/),
    [HPF](Filter/HPF/)
* [Chorus](Chorus/)
* TBC

##Testing
The test plan is documented [here](TestPlan/). Most of my analysis was carried-out using the brilliant [Sonic Visualiser](http://www.sonicvisualiser.org/) software.

##Resources
I found the following resources helpful for understanding the analogue synths.
* [URLs for Juno 60](Resources/Juno60/)
* [URLs for Juno 106](Resources/Juno106/) - has almost identical sound engine.
* [Books](Resources/Books/)
* [Web Audio API](Resources/WebAudioAPI/)

Any mistakes and misinterpretations are entirely my fault.

##Licensing
Copyright (c) 2015 Andy Harman and Pendragon Software Limited.

Released under the [MIT license](MIT-LICENSE.md). Please feel free to reuse the techniques developed in this project in your own projects.
