---
layout: post
title: hydrogeolog update
---

1. learning from TMA9548 i2c multiplexer

it is found that if all the sensors connected to 9548 are not powered at the same time,
9548 may become disfunctional if it attempts to read from sensors. such disfunctional phenomenon persists even if arduino is restarted. the only way to recover is to power off 9548 and back on.
the way of getting around this is switch on all the sensors before reading, and switched them off all once. one could also connect reset (5v) to downside switch, or simply do a power control


2. wish list form V2
   a.more holes for support the board
   b.reset arduino
   c.reverse switch for pi
   d.more nikkel area for the terminal block
   e.switch for voltage in switch
   f.more detail comments for pin holes
   g.reduce size
   h.commeing bolck to affiliated to anything on default
   i.reduce the width of the leads
   j.
