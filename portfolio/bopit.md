---
layout: default
title: Bop It! Rhythm Game
---

# {{ page.title }}

<div class="message">
 I worked on this project as part of EECS 149, the embedded systems class at UC Berkeley. This project involved creating a responsive real-time game entirely on low-power hardware. We modified a Bop It! device to input its buttons into the microcontroller. All the code is worked on collaboratively on <a href="github.com/onibrow/eecs149-proj">Github</a>.
</div>

<img src="/images/bopit.jpg" style="width:50%; float:right; margin-right:0.3rem; padding-left:0.8rem; border-radius:0">

This project involved creating a fun, polished, and responsive rhythm game that is all programmed in C. This allowed the game to be fast and responsive to register the player's hits and misses well. 

The technical aspects of this game include:

* Low-level programming
* Integration of separate devices
* Audio playback of MP3 through speakers
* Dealing with limited communication channels (I2C, SPI)
