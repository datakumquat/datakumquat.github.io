---
layout: post
title:  "Cat Meet Python"
date:   2023-01-26 23:34:56 +1300
categories: blog update
---
This house I live in does not have much in the way of garden; there are some loosely termed 'terraces' with native and Imported plants. Some lawn outside the front fence.

There is also a steep rear 'terrace' that is little more than a leftover from the original house construction.

Most of it has some grass, some plant-life and some texture to it. Except the bit next to the garage.

That is a sloping, 3 metre wide x 9 metre long desolate, clay & dirt space that grows nothing but weeds.

I keep it weed-free as much as possible, and so it is now the neighbourhood's Cat Toilet.

Of course it is ...

I've tried soft-drinks bottles with water, empty cans on pieces of string, pieces of hose, small piles of dead weeds, external sensor-lights ... all to no avail.

Unfortunately as an animal-lover I cannot consider lethal means, which leaves me Technology.

Having a rummage around this afternoon in my Raspberry Pi box, I found this:

  - 2 x Raspberry Pi-connectible Cameras
  - 5 x Raspberry Pi v3B+
  - 1 x Raspberry Pi v4
  - Networking gear
  - Spare car battery from the Garage
  - Python & OpenCV surveillance code that I wrote a few years back

**Project Cat Meet Python (CMP):**

  - Mission: Put together an adhoc but functional surveillence system
  - Components: Hardware listed above; Python; OpenCV; Chewing Gum
  - Task: Identify the miscreant Kitty(s) toileting in my yard
  - Data: Capture Images, Date/Time and Deposit details
  - Search: Build a web-fronted Database (PostGRES/SQL) for queries
  - Visualisation: Event Type; Frequency; Location; Subject (Bad Kitty)
  - Expansion: Motion-activated Hose Blast
  - Enhancements: Sound or Light Generation

That will do for a start, and since Tomorrow is the weekend, I can source, test and implement some simple frame-grabbing routines and go from there.

A great place to start with planning the camera control will be [Image and video recording with the Raspberry PI] or specifically [PiCamera].

In general there is so much quality RPi information on the WWW, that all it takes is some time, a RPi and some effort, and you can create almost anything. A great place to start reading on what to do with an RPi and Python is [The Raspberry Pi Guide for scientists and anyone else].

I can't wait.

Project CMP is a go.

**References:**

  - [Image and video recording with the Raspberry PI]
  - [PiCamera]
  - [The Raspberry Pi Guide for scientists and anyone else]

[Image and video recording with the Raspberry PI]: https://raspberrypi-guide.github.io/electronics/image-and-video-recording#recording-options-with-the-raspberry-pi/
[PiCamera]: https://picamera.readthedocs.io/en/release-1.13/
[The Raspberry Pi Guide for scientists and anyone else]: https://raspberrypi-guide.github.io/
