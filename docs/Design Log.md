# Electrical
 
- **why USB4604?** Microchip hub controllers had great documentation and application notes so I wanted to go with one of their options. When I started the project the only IC in stock on Mouser/Digikey was the USB4604. I found out when purchasing v1.1 that the USB2514 was available from LCSC for half the cost and a smaller package. Lesson learned...

- **why 4 layer board?** When designing v1.0, I saw that purchasing from JLCPCB at qty 5 was minimal cost difference between 2 vs 4 layer, so I started on a 4 layer stack. It was only when I tried to order at qty 15+ that I realized that JLCPCB added a fixed charge which significantly increased the cost. The design is definitely doable on a 2 layer board, but 4 layer gives a little more solution space. I didn't change to 2 layer for v1.1 because I didn't want to risk changing too much from my successful v1.0.

- **general workflow** I knew I wanted to make a USB Hub in the triangular shape of the Anduril logo, and make it as small as posisble to make it usbale as a usb hub. After importing the logo into solidworks I roughly got a rough housing drawn around the PCB. From there, I imported the PCB outline into KiCad and began designing. This was a big mistake because I still needed to fine tune the size and shape of the PCB and the housing. This meant I needed to redo the layout/routing eachtime I modified the housing. It would have been better if I had fully finalized the mechanicals of the housing and PCB and just did layout and routing one time. This isnt super realistic, but with some better understanding of the rough sizes of the components and one rough pass at just the layout, I couldve cut down a lot of design cycles by finishing the housing and pcb, and then finalizing the layout and completing the routing. additionally, i couldve probably spent more time finalizing the details of the housing (port openings, heat set insert sizing, clearances and interfaces). i spent a lot (too much) time exporting the pcb from KiCAD, to the housing file in Solidworks. Theres definitely some optimization to the workflow there that will ahppen naturally as my inuition and vision for designs improves. i'm very happy with how it turned out and learned a lot about the workflow and integration of pcbs and mechanical housings. the back and forth between KiCAD and SW was exacerbated by the tight constraints on the sizing.

after finalizing the pcb and housing design, i worked on optimizing the 3D printing of th housings since i was going to make 25. because of the qunaitiy, i couldn't modify each and every one in order to make it perfect, otherwise that would take too much time. so the parts need to come off the printer consistently and ready to be assembled. I had to dial in the support material settings to speed up the post processing and ensure consistent results visually. I could nest 3 sets of housings per build plate, which would take 7 hours to print. so by printing overnight, taking off in the morning and starting another print to run during the day. i could print 6 per 24 hours at a 100% yield rate! post processing time was about 3-5 mins per for support removal, heat set insert insertion, and any minor touchups.

- fuses on inputs (500mA upstream and 350mA downstream)
- tvs diodes on all inputs

- 4 layer board
    - signal
    - gnd
    - power
    - signal

- if i routed power i couldve done the perfereed stack of:
    - signal
    - gnd
    - gnd
    - signal

- 0805 components for handplacing, minimal benefit to smaller components
- did not do impedence matching, figured it would be fine without it and v1.0 worked fine without it. tried to match trace lengths. would like to understand more about impedence matching since it seems critical for robust designs

- needed to make housing tighter on pcb for better fit
- make heatset insert holes bigger to minimize the filament squeeze out
- wall thickness to match mulitple of nozzle thickness 

- 2 part housing seemed easiest to design
    - didnt see a need to hold down the PCB in any other way beyond the outer edges and connectors
    - easiest to print with minimal supports
- bumpon feet, hidden screws
- heat set inserts
- extra perimeters to minimize printed spikes that cause gaps in the housing

im sure theres a lot more i'm forgetting. will maybe add to this... please reach out with questions.
