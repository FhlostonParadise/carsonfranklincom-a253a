---
title: 3 Watt RGB Laser Projector
excerpt: >-
  Iceland is a Nordic country between the North Atlantic and the Arctic Ocean.
  It has a population of 325,671 and an area of 103,000 km2 (40,000 sq mi),
  making it the most sparsely populated country in Europe.
date: '2019-03-27'
thumb_img_path: images/7.jpg
thumb_img_alt: Icelandic horses
content_img_path: images/laser.jpg
content_img_alt: Icelandic horses
seo:
  title: Fragments of Iceland
  description: Iceland is a Nordic country between the North Atlantic and the Arctic Ocean.
  extra:
    - name: 'og:type'
      value: article
      keyName: property
    - name: 'og:title'
      value: Fragments of Iceland
      keyName: property
    - name: 'og:description'
      value: >-
        Iceland is a Nordic country between the North Atlantic and the Arctic
        Ocean.
      keyName: property
    - name: 'og:image'
      value: images/7.jpg
      keyName: property
      relativeUrl: true
    - name: 'twitter:card'
      value: summary_large_image
    - name: 'twitter:title'
      value: Fragments of Iceland
    - name: 'twitter:description'
      value: >-
        Iceland is a Nordic country between the North Atlantic and the Arctic
        Ocean.
    - name: 'twitter:image'
      value: images/7.jpg
      relativeUrl: true
layout: post
---
*Over the course of the 2020-2021 Pandemic I found myself with some extra time. Like many others, I took the opportunity to do some DIY projects. One of these (unlike many others) was a 3 Watt RGB Laser Projector system I built from (essentially) scratch. This post will be the narrative and thought process I put into it's design, build, and the lessons learned along the way.*

#### It is critically important that anyone working around or near lasers that operate above 5 milliwatts of output power know the risks associated with these devices. I cannot emphasize enough how dangerous these lasers can be. They have enough power to cause permanent and irreversible damage to your eyes in less time than it takes to blink.

When I used to play records in nightclubs and less "sanctioned" events I was always amazed at the laser systems the lighting guys would use. Something about a coherent beam of light cutting through the darkness that was amazing to me. With the lockdown from Covid-19 a lot of us had extra time to play with things. I did.

I started out bouncing a beam from a laser pointer off a mirror. It was where my interest would have normally stopped. Not this time.

![](/images/laser-mirror.png)

If you make the mirror move, you can take a single point, and expand it into a line. If the mirror is moving fast enough we perceive it as a continuous plane. If you add a 2nd mirror and move them equally, you create a circle. If you can manipulate the distance, time, and power of the laser you can draw anything you want. Shapes, letters, numbers, and cool patterns that look crazy if the beam is fully visible.

This seemed like the extent of the story. But I kept thinking that it would be awesome to make a full controlled system that could accept commands from a microcontroller and move accordingly. I started with an arduino and a couple stepper motors. I encountered my first set of problems.

*   The Motors cannot move fast enough to make what appears to be a solid line.

*   The voltage / current to the laser diode does not equal its brightness. It is either on, or off.

*   It is a nightmare to program.

I decided to move from stepper motors to something that can move much quicker. I settled on using the actuator arm from old hard drives. If I attach the mirror to the arm (I actually made the mirrors from the hard drive platter) and apply a voltage to the arm, it moves, and it moves fast.

{{< vimeo 527491922 >}}

From here on out it became a battle to control the actuator arm with enough precision that it would move and return to expected points. After some more research it became clear that while the galvanometers in the hard drive were working, they were not sufficient or capable of accurately steering the beam where I wanted. It was time to go shopping.

*Note: I used 1 power supply to power the galvo and amplifiers, and 1 to power everything else. I was starting to get a little close to pushing a single 15v to its limit. The 15v needs to send a +15v , and a -15v, along with a ground to the galvos. This is the voltage they operate at. Everything else was 12v.*

### Why not add more lasers?

Green is great. It is the most visible laser light to our eyes. But if we add a red laser in the 630nm wavelength and a blue laser in the 400'ish nm wavelength, we get a red + green + blue light which if balanced will make a pure white beam. This is the same basic color system we learn in graphic design.

### Combining Light is Difficult

How do we take 3 separate beams of light, and combine them into 1 that will maintain its coherence over a long distance? This was not easy and I wish I had looked more before trying to cook up a solution without assistance.

I first attempted to combine them using miscellaneous mirrors and prisms at different angles. I can make them all join, but not for long. The end result was always 3 beams that could start close, but diverge right after.

The solution?

Dichroic Glass.

This is a special glass that will reflect a certain wavelength of light while allowing all other wavelengths to pass through. Using these I was able to combine the 3 beams into a perfect coherent single beam with no divergence.

![test](/images/20210121\_153109.jpg)
