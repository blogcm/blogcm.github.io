---
layout: post
title: hydrogeolog update
---

1. learning from TMA9548 i2c multiplexer

it is found that if all the sensors connected to 9548 are not powered at the same time,
9548 may become disfunctional if it attempts to read from sensors. such disfunctional phenomenon persists even if arduino is restarted. the only way to recover is to power off 9548 and back on.
the way of getting around this is switch on all the sensors before reading, and switched them off all once. one could also connect reset (5v) to downside switch, or simply do a power control
