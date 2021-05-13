+++
title = "RingSeq"
date = 2020-07-01T14:37:49+01:00
draft = false
+++

# The Ring Sequencer

> This write up is intended as a brief introduction to the work we have done on [```pat```](https://github.com/muses-dmi/pat/) and the Ring Sequencer instrument until we are able to publish all the resources. Unfortunately, due to some unfortunate circumstances around the time of publishing, we have yet to publish the source for the project. We will aim to get this done as soon as possible - please reach out to us if you are keen to see it!

The ring sequencer is a small demo instrument related to the work in my paper on ['Digital Expression and Representation of Rhythm'](https://wint3rmute.com/research/amrhythm/). It was intended as a way for exploring polyrhythms in an interactive manner but also as a way for demonstrating how embedded domain specific programming languages can be used for directly generating physical parts of an instrument.

The premise of the ring sequencer is that marbles or ball bearings can be placed on interchangeable rings to trigger musical events. The instrument is implemented using a [Sensel Morph](https://sensel.com/pages/the-sensel-morph), with a 3D printed overlay. The rings slot into this overlay, and a small generator is supplied such that ```pat``` patterns can be written and turned into STL files, which can also be 3D printed.

This Ring Generator is written in Haskell, and takes a pattern and returns a ring. This is a somewhat trivial/toy example, however the concept is promising in terms of helping users design instruments in their entirety, using extensive, programmatic techniques.

![RingSeq](/ring.png)

Notably, the STL functionality is provided by another embedded DSL (ImplicitCAD.)