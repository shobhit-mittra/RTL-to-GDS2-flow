# Basics of Integrated-Circuits(IC) :

This first section of the course serves as an introduction to VLSI and the world of semiconductor ICs' that surrounds us in the form of electronic devices. This section is divided into **two** sub-sections where the [former sub-section](#sub1) discusses about the background of VLSI domain and it's importance; the [latter sub-section](#sub2) describes the 

<a id='sub1'> </a>
## Sub-Section I : Background of VLSI-Design

### VLSI : A Historic Perspective

Prior to the inception of ICs and the domain of VLSI, the earliest of the devices were engineered and designed by the interconnection of numerous discrete active* (diode, transistor) and passive* (resistor, capacitor, inductor) components.

> [!NOTE]
> Active components are the one's that require a source of energy to perform their functionality and passive components do not require any source of energy. 

The issue with such method of creating devices is the nexus of these discrete components becomes expensive, time-consuming and unreliable. In order to counter this issue, a technology was developed in the 1960s' namely : 'Integrated Circuit(IC)'. 

ICs' are monolithic silicon chip that contains several components on the chip. Monolithic in this context refers to the material composition for the base chip is homogenous i.e Silicon and only a single crystal is used. The transistors are realised on this single crystal of silicon itself rather than combining discrete components together.

One of the standard methodology to realise transistors on a silicon chip is Photolithography. 

> [!IMPORTANT]
> TBD

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





