# Basics of Integrated-Circuits(IC) :

This first section of the course serves as an introduction to VLSI and the world of semiconductor ICs' that surrounds us in the form of electronic devices. This section is divided into **two** sub-sections where the [former sub-section](#sub1) discusses about the background of VLSI domain and it's importance; the [latter sub-section](#sub2) describes the basics of ICs in brief.

<a id='sub1'> </a>
## Sub-Section I : Background of VLSI-Design

### VLSI : A Historic Perspective

Prior to the inception of ICs and the domain of VLSI, the earliest of the devices were engineered and designed by the interconnection of numerous discrete active* (diode, transistor) and passive* (resistor, capacitor, inductor) components.

> [!NOTE]
> Active components are the one's that require a source of energy to perform their functionality and passive components do not require any source of energy. 

The issue with such method of creating devices is the nexus of these discrete components becomes expensive, time-consuming and unreliable. In order to counter this issue, a technology was developed in the 1960s' namely : 'Integrated Circuit(IC)'. 

ICs' are monolithic silicon chip that contains several components on the chip. Monolithic in this context refers to the material composition for the base chip is homogenous i.e Silicon and only a single crystal is used. The transistors are realised on this single crystal of silicon itself rather than combining discrete components together.

One of the standard methodology to realise transistors on a silicon chip is Photolithography. 

> [!NOTE]
> Photolithography is discussed further ahead 

In response to the surge in the demand for ICs' due to the quest for higher computation and data storage, the number of transistors packaged on a single chip also increased. This led to the increase in the scale of integration to the point where millions of transistors are integrated on a single chip. This advancement paved way for the domain of **Very-Large-Scale-Integration (VLSI)**. 

The incrementation of packaging density for every new generation of a chip is due to the advancement in the technology node of transistors used in the pacakaging of the chip. Technology node or simply Technology, in this context, refers to the distance between the source and the drain that essentially forms the conducting channel in the transistor for flow of current. Advanced technology nodes have a smaller channel length that makes it possible to shrink the tranistor size and contribute to a higher number of transistor count onto a chip essentially increasing the packaging density. The incorporation of advancement of technology nodes improves it's **performance metrics** such as *speed*, *power dissipation*, *cost* etc. This process of shrinking the transistors is termed as **Scaling Down** of the transistors.

### Agenda 

So far from the discussion, it is safe to infer that scaling down the transistor technology is the future of computation. But this process introduces various challanges that increases the complexity of ICs' and impedes the designing process. The agenda of this course as mentioned by Professor Sneh Saurabh is to explore and understand these challanges and practically visualise ways to navigate through these obstacles faced by **VLSI engineers** through this road from *RTL-to-GDS*.

### Structure of Integrated Circuits :

Let's take a simple example of a CMOS-based inverter. The illustration(*Fig1.1*) below shows the structre of a CMOS inverter.

![Fig1.1 : CMOS Inverter](/images/theory/cmos_inv.png)

This simple cmos design represents a logical NOT-gate in digital design that simply provides an inverted output, i.e a logic 1 as an output when logic 0 is given as an input and vice-versa. This fundamental design can be realised as an integrated circuit as shown below in *Fig1.2*. 

![Fig1.2 : IC basic structure](/images/theory/basic_ic.png)

It is evident that the structure seems to look quite intimidating at first glance. The key insights that must be noted from the *Fig1.2* are as under :

- An IC comprises of multiple layers (In this case 2 metal layers). Layers such as : Diffusion, Implant, metal etc.
- Bottom Layer : Devices : This region consists of diodes, tranistors that constitute the device portion of the IC
- Above Devices : Interconnect layers of metal separated by insulators (Typically 6-10 metal layers in a typical IC)
- The Via are used to estabilish connection between metal layers.

A common question that may arise after the discussion of structure of IC is the need for having multiple layers, Why can't the structure be completely ?

To answer this lets examine a simple scenario described as under : 

![Fig1.3](/images/theory/ic_structure1.png)

Imagine a square region that has four components (A1,A2,B1,B2) at it's perimeter. The objective here is to connect A1,A2 and B1,B2 using two interconnects. The criteria to do this is postulated below :

- The interconnects must not go outside the square region described
- The interconnects must be in the same plane as the one containing A1,A2,B1,B2

Taking these conditions in consideration, is it possible to connect A1 to A2 and B1 to B2 without *shorting* the interconnects? 

![Fig1.4](/images/theory/ic_structure2.png)

It isn't possible to avoid shorting if the constraints mentioned are followed. What about relieving the **second** constraint? The constraint that forces the interconnects to be in the same plane.

![Fig1.5](/images/theory/ic_structure3.png)

The dotted line from A1 to A2, in the illustration, represents a connection using a metal layer (layer1) that resides in a different plane compared to metal layer2. Hence, multiple metal layers are necessary to estabilish connection between components that would otherwise short if implemented on a single layer.
These layers are defined using masks and fabricated using Photolithography.

### Photolithography : A Brief Insight

To put it in a simple way, it is the process of transferring geometric shapes that are defined on a mask to the surface of silicon wafer. These shapes define the layout of components, interconnects, and circuits, enabling the miniaturization, customization, and integration of electronic components on a chip. The illustration below shows the process in one-shot. 

![Fig1.6 : Photolithography](/images/theory/photolithography.png)


### Semiconductor Ecosystem : Designing vs Fabrication : 

Every VLSI-design flow can be broadly divided into these two aspects namely, Design and Fabrication. These are inter-dependant processes and are quite different from one another. 

![Fig1.7 : Designing vs Fabrication](/images/theory/designVfabrication.png)

- Designing involves determining the parameters and properties for a certian component in a circuit to achieve the desired functionality. Simply put, it's the planning phase to develop a desired circuit.

- Fabrication refers to using the parameters defined in the design phase and use them to realise the actual physical circuit in the form of IC. Hence, it's the implementation phase that follows the design phase.

Although Designing and Fabrication are done separately but they are highly inter-dependant on eachother. During designing it is important to take into consideration the properties such as delay, area, etc. for the technology that will be used to realise the design during fabrication. Hence, it is crucial that there exists a medium of exchange of intel between these two faction. The illustration below shows the ecosystem. 

![Fig1.8 : Semicon Ecosystem](/images/theory/semicon_ecosystem.png)

The information is shared using :

- PDK(Process Design Kit) that is provided by the foundry to the design team. PDK contains crucial information about the technology that'll be used for fabrication and Design Rule Checks (DRC) that must be taken care of while designing.

- Design (Layout) is provided by the design team to the foundry in the form of a GDSII file (Graphic Design System Information Interchange) for fabrication.


### Semiconductor Industry : Business Model

The semiconductor ecosystem sustains majorly via three types of companies that are mentioned below :

![Fig1.9 : Semicon Business Model](/images/theory/semicon_business_model.png)

1. Fabless Design Companies :
- Only into designing , fabrication is outsourced
- Does not require to setup expenisve foundries
- Eg : NVIDIA, Qualcomm, Broadcomm

2. Merchant Foundries :
- Only involved in fabrication for fabless companies
- Eg : TSMC, UMC, GF etc.

3. Integrated Device Manufacturers :
- Designing + Fabrication done in same company
- Production is more cost-efficient due to control over all steps in the entire flow
- Eg : Intel, Samsung Electronics
</br>

<a id='sub2'> </a>
## Sub-Section II : Basic Concepts of Integrated Circuits 

### Types of Integrated Circuits :

ICs can be primarily classified using the catagories as under :

- [On the Basis of Application](#app)
- [On the Basis of Design Style](#design_style)

<a id='app'></a>
#### Application-Based
This is further classified into : 

1. Application Specific Integrated Circuits (ASICs)
2. General Purpose Integrated Circuits 

To briefly explain the differences between the two :

Some properties of ASIC :
- Chip designed to perform as a particular end system
- They are non-programmable and hence fail to deversify the range of their usage
- Their volume of production is relatively limited
- Example : IC for Camera, IC for graphic cards (AMD Radeon - NVIDIA graphic cards) etc.

Some properties of General Purpose Integrated Circuits :
- Chip designed to perform as a wide-range end system
- They are programmable via software and hence deversify the range of their usage
- Their volume of production is relatively larger
- Example : Microprocessors, Memories, FPGA

<a id='design_style'></a>
#### Design-Style-Based
This is further classified into :


1. Full-Custom Design
2. Standard-Cell Based Design (Semi-Custom)
3. Gate Array Based Design
4. Field-Programmable Gate Array (FPGA)

The table below briefly explain the differences among the four :


| Parameters | Full-Custom Design | Semi-Custom Design | Gate-Array Design | FPGA |
| :--------: | :----------------: | :----------------: | :---------------: | :--: |
| Description | Design Specfic Customisation at the transistor level | Pre-designed standard cells/macros and the interconnections b/w these pre-designed cells are design specific | Transistor placement predefined on wafer, interconnects are design-specific | Programmable logic blocks and interconnects|
| Design Effort | Maximum | High | Lower | Lower |
| Custom Mask Layers | All | All | Top few layers | None |
| Performance, Power, Area | Best | Very Good | Comparitively Inferior |Comparitively Inferior | 


> [!NOTE]
> The major focus for this course would be towards Standard-Cell based Design or Semi-Custom Design










