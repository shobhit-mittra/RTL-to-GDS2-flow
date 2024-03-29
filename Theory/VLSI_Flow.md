# Overview of VLSI-Design Flow :

After covering the [basic concepts of IC](../Theory/Basics_of_IC.md), we move onto explore the VLSI-Design flow in detail and all the related concepts. 


## VLSI Flow : A top-level view

The journey of a design starting from it's ideation all the way to fabrication of the chip is one that is long and tedious. 

![Fig2.1 : Idea to Chip](/images/theory/idea_to_chip.png)

It is wise to utilize the technique of *divide-and-conquer* to familiarize and comprehend this wonderful flow. As the name suggests, divide-and-conquer involves breaking down the flow into smaller and simpler segments. A big upside to this ordeal is that it becomes even more apparent how each segment interacts with one another and their influence on eachother - Like carrying out optimization in early stages of the design-flow can lead to other stages down the flow to become more managable and hence improving efficiency. 

![Fig2.2 : VLSI top view](/images/theory/vlsi_divide_conquer.png)

The image above shows a simplified view of the VLSI-flow including fabrication. The important takeaway from the illustration :
- RTL refers to a hardware descriptive language : Verilog, VHDL etc.
- GDS : Graphic Database System (Layout)
- Pre-RTL flow (Idea to RTL) : takes a high-level idea/concept of a product and represents the hardware portion of the implementation in RTL
- RTL-to-GDS flow involves taking the RTL through various stages of logical and physical design to finally reach the GDS file
- Post-GDS flow (GDS to Chip) : prepares mask for the obtained GDS and perform fabrication/testing/packaging

## Abstraction :

