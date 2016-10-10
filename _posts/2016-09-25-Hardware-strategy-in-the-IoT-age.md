---
layout: post
title: Hardware strategies for the IoT age
---

IoT is a complex mess... and yet [many estimate that it will be a
"multi-trillion-sized" mess over the next decade][1]. 
Like all complex systems, we must develop simplified models to understand them.
This is mine.

Internet   of     Things
             =
(1) Devices (2) Connected  to (3) the Cloud 

Devices
=======

This can be pretty much anything that can measure or interact with the physical
world, and (key detail) connect to the Internet.  This encompasses a vast
diversity of "things".  And this is the main problem with the IoT: it is too vague and fragmented. 

One way to break down all the possible types of devices, is according to where
they are deployed, their "setting".  This is a classification proposed by McKinsey:

  1. Human
  1. Home
  1. Retail
  1. Offices
  1. Factories
  1. Worksites
  1. Vehicles
  1. Cities
  1. Outside

And in each setting there can be hundreds of different devices.  So, regardless
of how big the IoT space is, it will be very unlikely that one single device
can capture a significant portion of the market. 

One thing is clear, devices age rapidly and scale poorly.  But there are the
*entry point into the data value chain*, so these problems must be embraced and
solved in order to have a successful business (more on this later...). 

Connectivity
=====

How do devices connect to the internet?  Depending on the setting the options
vary.  Static devices that are deployed in connected locations have it the
easiest:  WiFi or wired channels provide cheap, high-bandwith pipes to the
cloud.

What about truly mobile devices?  The only wide area network that
is truly mobile is cellular.  This highly regulated sector has been able to
[extract healthy margins][2] over the years. 

However, the irruption of IoT is forcing a change of rules.  A network that was
designed for voice has had to adapt rapidly to very different use cases, from
bandwidth-hogging smartphones to ultra low duty-cycle sensors.  Services that used to
be the monopolized by cellular operators, such as voice messaging or SMS, can
now be replaced by much cheaper cloud services.  And there is no turning back:
the new IP-based cellular networks leave little room for proprietary silos.

Cloud
=====

Cloud players, have a different story than *Devices* and *Connectivity*.
Regardless of the type of IoT device, chances are that the data it generates
will end up in the data centers of one of 4 companies: Google, Amazon,
Microsoft or Baidu.  These companies will clearly benefit the most
from the IoT revolution.

Will they "own" the IoT space?  They certainly face less competition and higher
margins than the other segments.  But ultimately, they do need to have access
to the data gathered by devices (and to make sense of it) to provide true
value. And for that they need the approval of the Device maker.

So we have come full circle:

1. Devices produce data, but they are expensive to build and hard to scale.
2. Cellular networks transport the data, but cannot provide exclusive services in the new IP-based architecture. 
3. Few cloud players concentrate most of the IoT data, but cannot exploit it without the Device maker approval.

Our plan for success
==============

1. Minimize device complexity
2. Leverage IP techologies over cellular
3. Hold on to the data and derived intelligence

References
==========

[1]: http://www.mckinsey.com/business-functions/business-technology/our-insights/the-internet-of-things-the-value-of-digitizing-the-physical-world 
[1] "The Internet of Things: Mapping the value beyond the hype", McKinsey & Company Report, June 2015

[2]: https://ycharts.com/companies/VZ/gross_profit_margin
[2] Verizon Gross Margins

[3]: http://www.barrons.com/articles/winners-in-the-internet-of-things-1452316081
[3] Winners in the Internet of Things, Barron's, January 9, 2016

[4]: http://marketrealist.com/2015/01/overview-us-telecom-industry/
[4] Overview of the US Telecom Industry, January 2015
