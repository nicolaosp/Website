---
title: A regional model of the Romanche Fracture Zone
date: '2026-10-29'
blog:
  - Romanche Fracture Zone
---

The **Romanche Fracture Zone**, is the third deepest trench of the Atlantic Ocean and sits roughly at the Equator. It is believed to be the meeting point of deep Atlantic waters-originating from the North pole-and Antartic bottom waters, and hence an important place for mixing of the physical, chemical and biological properties of these two water masses. It is believed to be full of nutrients for deep-ocean life to thrive. 

In october 2026, I had the chance to take part in a research expedition on board Falkor (too)—the research vessel of the Schmidt Ocean Institute—with a team of 25 biologists, geologists and physical oceanagraphers to go check this hypothesis, **further our understanding of water mass mixing in the Romanche Fracture Zone, and explore benthic life in this region**. 

![Falkor (too)](Images/Falkor_too.JPG)
*Research vessel Falkor (too).*

While on board, I developed a regional model of the Romanche Fracture Zone that includes both dynamical and biogeochemical processes. The model is based on the [NumericalEarth](https://github.com/NumericalEarth) framework that allows for the development of flexible simulations coupling the atmosphere, ocean, and land systems. Thanks to the NumericalEarth for putting together such a powerful tool. 

I designed a coupled atmosphere-ocean simulation. The atmosphere is prescribed by the JRA55 reanalysis. The ocean part of the model solved for the non-hydrostatic equation of motion, forced at the boundaries by the GLORYS reanalysis dataset. The biogeochemical components included a populations of zoo- and phytoplanktons, nutrients (nitrate, phosphate, and silicate), carbonate and oxygen chemistry. 

The model runs on GPU; a few months of simulations only need a few hours of compute on a single GPU (NVIDIA® GeForce RTX™ 5060 8GB GDDR7). I was able to run the model while onboard, update it daily to cater the needs of the research team. Importantly, the model was instrumental in refining the sampling strategies. 

![Surface fields BGC](Images/Surface_fields_BGC.jpg)
*Surface biogeochemical fields, as predicted by the model.*

The code is available on [Github](https://github.com/nicolaosp/LifeRomancheFractureZone). 
