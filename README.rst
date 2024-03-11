General
=======

Scope
-----

This document describes the design rules for IHPs SG13G2 SiGe BiCMOS
technology.

List of Abbreviations
---------------------

.. table:: List of abbreviations used within this document

   ================ =================================================
   **Abbreviation** **Explanation**
   ================ =================================================
   BiCMOS           Bipolar CMOS
   HBT              Heterojunction Bipolar Transistor
   IC               Integrated Circuit
   IHP              Innovations for High Performance Microelectronics
   MIM              Metal-Insulator-Metal
   NMOS             Negative Channel Metal Oxide Semiconductor
   PMOS             Positive Channel Metal Oxide Semiconductor
   RD               Reference Document
   SiGe             Silicon Germanium
   ================ =================================================

.. _`s:reference_docs`:

Reference Documents
-------------------

[RD 1] IHP SG13G2 Open Source Process Specification Rev. 1.2

.. _`c:layertable`:

Layer Table
===========

This chapter is a documentation of IHP layers definition which is valid
in all technologies.

**Remark:** Only the layers described in the following table are allowed
to be used in layout designs. Do not use layers exclusively reserved for
internal usage.

+---+---------+---+---+-----------------------------------------------+
|   | drawing |   |   | Defines active regions in substrate, where    |
|   |         |   |   | transistors, diodes and/or capacitors will be |
|   |         |   |   | fabricated                                    |
+---+---------+---+---+-----------------------------------------------+
|   | pin     |   |   | Activ pin layer                               |
+---+---------+---+---+-----------------------------------------------+
|   | mask    |   |   | added to Active:drawing at mask generation    |
+---+---------+---+---+-----------------------------------------------+
|   | filler  |   |   | Activ filler layer                            |
+---+---------+---+---+-----------------------------------------------+
|   | nofill  |   |   | Activ filler exclusion layer                  |
+---+---------+---+---+-----------------------------------------------+
|   | OPC     |   |   | Activ outer OPC definition layer              |
+---+---------+---+---+-----------------------------------------------+
|   | iOPC    |   |   | Activ inner OPC definition layer              |
+---+---------+---+---+-----------------------------------------------+
|   | noqrc   |   |   | No parasitics extraction                      |
+---+---------+---+---+-----------------------------------------------+
|   | drawing |   |   | Defines active npn collector region           |
+---+---------+---+---+-----------------------------------------------+
|   | OPC     |   |   | BiWind OPC definition layer                   |
+---+---------+---+---+-----------------------------------------------+
|   | drawing |   |   | Defines polysilicon gates and interconnect    |
+---+---------+---+---+-----------------------------------------------+
|   | pin     |   |   | GatPoly pin layer                             |
+---+---------+---+---+-----------------------------------------------+
|   | filler  |   |   | GatPoly filler layer                          |
+---+---------+---+---+-----------------------------------------------+
|   | nofill  |   |   | GatPoly filler exclusion layer                |
+---+---------+---+---+-----------------------------------------------+
|   | OPC     |   |   | GatPoly outer OPC definition layer            |
+---+---------+---+---+-----------------------------------------------+
|   | iOPC    |   |   | GatPoly inner OPC definition layer            |
+---+---------+---+---+-----------------------------------------------+
|   | noqrc   |   |   | No parasitics extraction                      |
+---+---------+---+---+-----------------------------------------------+
|   | drawing |   |   | Defines 1-st metal contacts to Activ, GatPoly |
+---+---------+---+---+-----------------------------------------------+
|   | OPC     |   |   | Cont OPC definition layer                     |
+---+---------+---+---+-----------------------------------------------+
|   | drawing |   |   | Defines areas to receive P+ source/drain      |
|   |         |   |   | implant                                       |
+---+---------+---+---+-----------------------------------------------+
|   | block   |   |   | Defines areas which do not receive S/D        |
|   |         |   |   | implants                                      |
+---+---------+---+---+-----------------------------------------------+
|   | drawing |   |   | Defines 1-st metal interconnect               |
+---+---------+---+---+-----------------------------------------------+
|   | pin     |   |   | Metal1 pin layer                              |
+---+---------+---+---+-----------------------------------------------+
|   | mask    |   |   | added to Metal1:drawing at mask generation    |
+---+---------+---+---+-----------------------------------------------+
|   | filler  |   |   | Metal1 filler layer                           |
+---+---------+---+---+-----------------------------------------------+
|   | nofill  |   |   | Metal1 filler exclusion layer                 |
+---+---------+---+---+-----------------------------------------------+
|   | slit    |   |   | Metal1 slit definition layer                  |
+---+---------+---+---+-----------------------------------------------+
|   | text    |   |   | Text layer for Metal1, used for LVS           |
+---+---------+---+---+-----------------------------------------------+
|   | OPC     |   |   | Metal1 OPC definition layer                   |
+---+---------+---+---+-----------------------------------------------+
|   | noqrc   |   |   | No parasitics extraction                      |
+---+---------+---+---+-----------------------------------------------+
|   | res     |   |   | Wire resistor                                 |
+---+---------+---+---+-----------------------------------------------+
|   | iprobe  |   |   | Current probe                                 |
+---+---------+---+---+-----------------------------------------------+
|   | diffprb |   |   | Differential current probe                    |
+---+---------+---+---+-----------------------------------------------+
|   | drawing |   |   | Defines regions where passivation coating is  |
|   |         |   |   | removed                                       |
+---+---------+---+---+-----------------------------------------------+
|   | pin     |   |   | Passiv pin layer                              |
+---+---------+---+---+-----------------------------------------------+
|   | sbump   |   |   | Defines passivation openings for solder bump  |
|   |         |   |   | bonding                                       |
+---+---------+---+---+-----------------------------------------------+
|   | pillar  |   |   | Defines passivation openings for copper       |
|   |         |   |   | pillar formation                              |
+---+---------+---+---+-----------------------------------------------+
|   | pdl     |   |   | Plasma dicing line                            |
+---+---------+---+---+-----------------------------------------------+
|   | drawing |   |   | Defines 2-nd metal interconnect               |
+---+---------+---+---+-----------------------------------------------+
|   | pin     |   |   | Metal2 pin layer                              |
+---+---------+---+---+-----------------------------------------------+
|   | mask    |   |   | added to Metal2:drawing at mask generation    |
+---+---------+---+---+-----------------------------------------------+
|   | filler  |   |   | Metal2 filler layer                           |
+---+---------+---+---+-----------------------------------------------+
|   | nofill  |   |   | Metal2 filler exclusion layer                 |
+---+---------+---+---+-----------------------------------------------+
|   | slit    |   |   | Metal2 slit definition layer                  |
+---+---------+---+---+-----------------------------------------------+
|   | text    |   |   | Text layer for Metal2, used for LVS           |
+---+---------+---+---+-----------------------------------------------+
|   | OPC     |   |   | Metal2 OPC definition layer                   |
+---+---------+---+---+-----------------------------------------------+
|   | noqrc   |   |   | No parasitics extraction                      |
+---+---------+---+---+-----------------------------------------------+
|   | res     |   |   | Wire resistor                                 |
+---+---------+---+---+-----------------------------------------------+
|   | iprobe  |   |   | Current probe                                 |
+---+---------+---+---+-----------------------------------------------+
|   | diffprb |   |   | Differential current probe                    |
+---+---------+---+---+-----------------------------------------------+
|   | drawing |   |   | Defines npn base poly region                  |
+---+---------+---+---+-----------------------------------------------+
|   | pin     |   |   | BasPoly pin layer                             |
+---+---------+---+---+-----------------------------------------------+
|   | drawing |   |   | Defines areas to receive P+ source/drain      |
|   |         |   |   | implant                                       |
+---+---------+---+---+-----------------------------------------------+
|   | drawing |   |   | Reserved for internal LDMOS development       |
+---+---------+---+---+-----------------------------------------------+
|   | drawing |   |   | surrounds areas were digital DRC is valid     |
+---+---------+---+---+-----------------------------------------------+
|   | drawing |   |   | Defines 1-st metal to 2-nd metal contact      |
+---+---------+---+---+-----------------------------------------------+
|   | drawing |   |   | Defines 1-st back-side metal interconnect     |
+---+---------+---+---+-----------------------------------------------+
|   | pin     |   |   | BackMetal1 pin layer                          |
+---+---------+---+---+-----------------------------------------------+
|   | mask    |   |   | added to BackMetal1:drawing at mask           |
|   |         |   |   | generation                                    |
+---+---------+---+---+-----------------------------------------------+
|   | filler  |   |   | BackMetal1 filler layer                       |
+---+---------+---+---+-----------------------------------------------+
|   | nofill  |   |   | BackMetal1 filler exclusion layer             |
+---+---------+---+---+-----------------------------------------------+
|   | slit    |   |   | BackMetal1 slit definition layer              |
+---+---------+---+---+-----------------------------------------------+
|   | text    |   |   | Text layer for BackMetal1, used for LVS       |
+---+---------+---+---+-----------------------------------------------+
|   | OPC     |   |   | BackMetal1 OPC definition layer               |
+---+---------+---+---+-----------------------------------------------+
|   | noqrc   |   |   | No parasitics extraction                      |
+---+---------+---+---+-----------------------------------------------+
|   | res     |   |   | Wire resistor                                 |
+---+---------+---+---+-----------------------------------------------+
|   | iprobe  |   |   | Current probe                                 |
+---+---------+---+---+-----------------------------------------------+
|   | diffprb |   |   | Differential current probe                    |
+---+---------+---+---+-----------------------------------------------+
|   | drawing |   |   | Defines regions where passivation coating is  |
|   |         |   |   | removed                                       |
+---+---------+---+---+-----------------------------------------------+
|   | drawing |   |   | Identifies resistor areas                     |
+---+---------+---+---+-----------------------------------------------+
|   | drawing |   |   | Identifies memory areas                       |
+---+---------+---+---+-----------------------------------------------+
|   | drawing |   |   | Identifies bipolar transistor areas           |
+---+---------+---+---+-----------------------------------------------+
|   | drawing |   |   | Identifies inductor areas                     |
+---+---------+---+---+-----------------------------------------------+
|   | pin     |   |   | IND pin layer                                 |
+---+---------+---+---+-----------------------------------------------+
|   | text    |   |   |                                               |
+---+---------+---+---+-----------------------------------------------+
|   | drawing |   |   | Defines non salicided Activ and GatPoly,      |
|   |         |   |   | BasPoly areas                                 |
+---+---------+---+---+-----------------------------------------------+
|   | drawing |   |   | Defines 2-nd metal to 3-rd metal contact      |
+---+---------+---+---+-----------------------------------------------+
|   | drawing |   |   | Defines 3-rd metal interconnect               |
+---+---------+---+---+-----------------------------------------------+
|   | pin     |   |   | Metal3 pin layer                              |
+---+---------+---+---+-----------------------------------------------+
|   | mask    |   |   | added to Metal3:drawing at mask generation    |
+---+---------+---+---+-----------------------------------------------+
|   | filler  |   |   | Metal3 filler layer                           |
+---+---------+---+---+-----------------------------------------------+
|   | nofill  |   |   | Metal3 filler exclusion layer                 |
+---+---------+---+---+-----------------------------------------------+
|   | slit    |   |   | Metal3 slit definition layer                  |
+---+---------+---+---+-----------------------------------------------+
|   | text    |   |   | Text layer for Metal3, used for LVS           |
+---+---------+---+---+-----------------------------------------------+
|   | OPC     |   |   | Metal3 OPC definition layer                   |
+---+---------+---+---+-----------------------------------------------+
|   | noqrc   |   |   | No parasitics extraction                      |
+---+---------+---+---+-----------------------------------------------+
|   | res     |   |   | Wire resistor                                 |
+---+---------+---+---+-----------------------------------------------+
|   | iprobe  |   |   | Current probe                                 |
+---+---------+---+---+-----------------------------------------------+
|   | diffprb |   |   | Differential current probe                    |
+---+---------+---+---+-----------------------------------------------+
|   | drawing |   |   | Defines the regions that receive P-Channel VT |
|   |         |   |   | adjust, P-Channel Punch-Through and N-Well    |
|   |         |   |   | implants                                      |
+---+---------+---+---+-----------------------------------------------+
|   | pin     |   |   | NWell pin layer                               |
+---+---------+---+---+-----------------------------------------------+
|   | drawing |   |   | Defines bipolar sub collector and isolated    |
|   |         |   |   | NMOS devices                                  |
+---+---------+---+---+-----------------------------------------------+
|   | pin     |   |   | nBuLay pin Layer                              |
+---+---------+---+---+-----------------------------------------------+
|   | block   |   |   | Defines areas where no nBuLay implant is      |
|   |         |   |   | allowed                                       |
+---+---------+---+---+-----------------------------------------------+
|   | drawing |   |   | Defines npn emitter window                    |
+---+---------+---+---+-----------------------------------------------+
|   | OPC     |   |   | EmWind OPC definition layer                   |
+---+---------+---+---+-----------------------------------------------+
|   | drawing |   |   | Defines deep collector regions                |
+---+---------+---+---+-----------------------------------------------+
|   | drawing |   |   | Defines Metal-Insulator-Metal capacitor area  |
+---+---------+---+---+-----------------------------------------------+
|   | drawing |   |   | Edge Seal definition layer, reserved for      |
|   |         |   |   | internal use only                             |
+---+---------+---+---+-----------------------------------------------+
|   | drawing |   |   | Substrate recognition layer for LVS           |
+---+---------+---+---+-----------------------------------------------+
|   | text    |   |   | Substrate recognition text for LVS            |
+---+---------+---+---+-----------------------------------------------+
|   | drawing |   |   | Pad recognition layer                         |
+---+---------+---+---+-----------------------------------------------+
|   | pillar  |   |   | Copper pillar pad recognition layer           |
+---+---------+---+---+-----------------------------------------------+
|   | sbump   |   |   | Solder bump pad recognition layer             |
+---+---------+---+---+-----------------------------------------------+
|   | drawing |   |   | Thick Gate Oxide                              |
+---+---------+---+---+-----------------------------------------------+
|   | drawing |   |   | Reserved for internal LDMOS development       |
+---+---------+---+---+-----------------------------------------------+
|   | drawing |   |   | Reserved for internal use                     |
+---+---------+---+---+-----------------------------------------------+
|   | pin     |   |   | Pwell pin layer                               |
+---+---------+---+---+-----------------------------------------------+
|   | block   |   |   | Defines areas where no well implants are      |
|   |         |   |   | allowed PWL:=NOT(NWell OR PWellBlock)         |
+---+---------+---+---+-----------------------------------------------+
|   | drawing |   |   | Reserved for internal use                     |
+---+---------+---+---+-----------------------------------------------+
|   | drawing |   |   | Defines 3-rd metal to 4-th metal contact      |
+---+---------+---+---+-----------------------------------------------+
|   | drawing |   |   | Defines 4-th metal interconnect               |
+---+---------+---+---+-----------------------------------------------+
|   | pin     |   |   | Metal4 pin layer                              |
+---+---------+---+---+-----------------------------------------------+
|   | mask    |   |   | added to Metal4:drawing at mask generation    |
+---+---------+---+---+-----------------------------------------------+
|   | filler  |   |   | Metal4 filler layer                           |
+---+---------+---+---+-----------------------------------------------+
|   | nofill  |   |   | Metal4 filler exclusion layer                 |
+---+---------+---+---+-----------------------------------------------+
|   | slit    |   |   | Metal4 slit definition layer                  |
+---+---------+---+---+-----------------------------------------------+
|   | text    |   |   | Text layer for Metal4, used for LVS           |
+---+---------+---+---+-----------------------------------------------+
|   | OPC     |   |   | Metal4 OPC definition layer                   |
+---+---------+---+---+-----------------------------------------------+
|   | noqrc   |   |   | No parasitics extraction                      |
+---+---------+---+---+-----------------------------------------------+
|   | res     |   |   | Wire resistor                                 |
+---+---------+---+---+-----------------------------------------------+
|   | iprobe  |   |   | Current probe                                 |
+---+---------+---+---+-----------------------------------------------+
|   | diffprb |   |   | Differential current probe                    |
+---+---------+---+---+-----------------------------------------------+
|   | drawing |   |   | Defines heat source for transistors           |
+---+---------+---+---+-----------------------------------------------+
|   | drawing |   |   | Defines heat source for resistors             |
+---+---------+---+---+-----------------------------------------------+
|   | drawing |   |   | Fluidic back side etch                        |
+---+---------+---+---+-----------------------------------------------+
|   | drawing |   |   | Defines npn emitter poly region and pnp base  |
|   |         |   |   | poly region                                   |
+---+---------+---+---+-----------------------------------------------+
|   | drawing |   |   | Substrate recognition layer for LVS           |
+---+---------+---+---+-----------------------------------------------+
|   | drawing |   |   | Excludes areas from design rule checking.     |
|   |         |   |   | Designs with NoDRC are rejected!              |
+---+---------+---+---+-----------------------------------------------+
|   | drawing |   |   | Macrocell name, element text layer            |
+---+---------+---+---+-----------------------------------------------+
|   | drawing |   |   | Defines 4-th metal to 5-th metal contact      |
+---+---------+---+---+-----------------------------------------------+
|   | drawing |   |   | Defines 5-th metal interconnect               |
+---+---------+---+---+-----------------------------------------------+
|   | pin     |   |   | Metal5 pin layer                              |
+---+---------+---+---+-----------------------------------------------+
|   | mask    |   |   | added to Metal5:drawing at mask generation    |
+---+---------+---+---+-----------------------------------------------+
|   | filler  |   |   | Metal5 filler layer                           |
+---+---------+---+---+-----------------------------------------------+
|   | nofill  |   |   | Metal5 filler exclusion layer                 |
+---+---------+---+---+-----------------------------------------------+
|   | slit    |   |   | Metal5 slit definition layer                  |
+---+---------+---+---+-----------------------------------------------+
|   | text    |   |   | Text layer for Metal5                         |
+---+---------+---+---+-----------------------------------------------+
|   | OPC     |   |   | Metal5 OPC definition layer                   |
+---+---------+---+---+-----------------------------------------------+
|   | noqrc   |   |   | No parasitics extraction                      |
+---+---------+---+---+-----------------------------------------------+
|   | res     |   |   | Wire resistor                                 |
+---+---------+---+---+-----------------------------------------------+
|   | iprobe  |   |   | Current probe                                 |
+---+---------+---+---+-----------------------------------------------+
|   | diffprb |   |   | Differential current probe                    |
+---+---------+---+---+-----------------------------------------------+
|   | drawing |   |   | Defines regions where special radiation hard  |
|   |         |   |   | design rules are applied                      |
+---+---------+---+---+-----------------------------------------------+
|   | drawing |   |   | Defines position of RFMEMS cap                |
+---+---------+---+---+-----------------------------------------------+
|   | drawing |   |   | Well implant for varicap devices              |
+---+---------+---+---+-----------------------------------------------+
|   | drawing |   |   | Via on top of interposer’s TopMetal2          |
+---+---------+---+---+-----------------------------------------------+
|   | drawing |   |   | Metal connected to IntBondVia                 |
+---+---------+---+---+-----------------------------------------------+
|   | drawing |   |   | Via on top of device’s TopMetal2              |
+---+---------+---+---+-----------------------------------------------+
|   | drawing |   |   | Metal connected to DevBondVia                 |
+---+---------+---+---+-----------------------------------------------+
|   | drawing |   |   | Deep trench from front side for plasma dicing |
|   |         |   |   | approach                                      |
+---+---------+---+---+-----------------------------------------------+
|   | drawing |   |   | Redistribution layer for metal wiring after   |
|   |         |   |   | chip IO                                       |
+---+---------+---+---+-----------------------------------------------+
|   | drawing |   |   | 1st graphene layer                            |
+---+---------+---+---+-----------------------------------------------+
|   | drawing |   |   | 2nd graphene layer                            |
+---+---------+---+---+-----------------------------------------------+
|   | drawing |   |   | Deep via between TopMetal2 and AntMetal1      |
+---+---------+---+---+-----------------------------------------------+
|   | drawing |   |   | Extra second-metal layer for antenna and      |
|   |         |   |   | passive integration                           |
+---+---------+---+---+-----------------------------------------------+
|   | drawing |   |   | GraphBot, GraphTop and GraphGat to            |
|   |         |   |   | GraphMetal1 or GraphMet1L contact             |
+---+---------+---+---+-----------------------------------------------+
|   | drawing |   |   | Backend integrated Si waveguide               |
+---+---------+---+---+-----------------------------------------------+
|   | filler  |   |   | SiWG filler layer                             |
+---+---------+---+---+-----------------------------------------------+
|   | nofill  |   |   | SiWG filler exclusion layer                   |
+---+---------+---+---+-----------------------------------------------+
|   | drawing |   |   | Si waveguide etching layer                    |
+---+---------+---+---+-----------------------------------------------+
|   | drawing |   |   | SiN waveguide etching layer                   |
+---+---------+---+---+-----------------------------------------------+
|   | drawing |   |   | Additional passivation for graphene           |
|   |         |   |   | structures                                    |
+---+---------+---+---+-----------------------------------------------+
|   | drawing |   |   | Defines G3 npn emitter window                 |
+---+---------+---+---+-----------------------------------------------+
|   | drawing |   |   | Defines G3 HV npn emitter window              |
+---+---------+---+---+-----------------------------------------------+
|   | drawing |   |   | Burried Layer with reduced dose for isolated  |
|   |         |   |   | NLDMOS                                        |
+---+---------+---+---+-----------------------------------------------+
|   | drawing |   |   | Extraction recognition layer for special CMOS |
|   |         |   |   | devices                                       |
+---+---------+---+---+-----------------------------------------------+
|   | drawing |   |   | Passivation opening                           |
+---+---------+---+---+-----------------------------------------------+
|   | drawing |   |   | Reserved for future use                       |
+---+---------+---+---+-----------------------------------------------+
|   | pin     |   |   | Polimide pin layer                            |
+---+---------+---+---+-----------------------------------------------+
|   | drawing |   |   | general device recognition shape for device   |
|   |         |   |   | extraction                                    |
+---+---------+---+---+-----------------------------------------------+
|   | pin     |   |   | General device pin recognition layer          |
+---+---------+---+---+-----------------------------------------------+
|   | esd     |   |   | ESD device recognition layer                  |
+---+---------+---+---+-----------------------------------------------+
|   | diode   |   |   | Active diode recognition layer                |
+---+---------+---+---+-----------------------------------------------+
|   | tsv     |   |   | TSV device recognition layer                  |
+---+---------+---+---+-----------------------------------------------+
|   | iprobe  |   |   | Current probe                                 |
+---+---------+---+---+-----------------------------------------------+
|   | diffprb |   |   | Differential current probe                    |
+---+---------+---+---+-----------------------------------------------+
|   | pillar  |   |   | Copper pillar pad recognition layer           |
+---+---------+---+---+-----------------------------------------------+
|   | sbump   |   |   | Solder bump pad recognition layer             |
+---+---------+---+---+-----------------------------------------------+
|   | otp     |   |   | OTP device recognition layer                  |
+---+---------+---+---+-----------------------------------------------+
|   | pdiode  |   |   | Enables extraction of parasitic diodes        |
+---+---------+---+---+-----------------------------------------------+
|   | mom     |   |   | Metal-on-metal (MOM) capacitor recognition    |
|   |         |   |   | layer                                         |
+---+---------+---+---+-----------------------------------------------+
|   | pcm     |   |   | Process control structure recognition layer   |
+---+---------+---+---+-----------------------------------------------+
|   | drawing |   |   | Defines additional collector opening in SG13  |
|   |         |   |   | HBTs                                          |
+---+---------+---+---+-----------------------------------------------+
|   | drawing |   |   | Graphene-metal standard interconnect          |
+---+---------+---+---+-----------------------------------------------+
|   | filler  |   |   | GraphMetal1 filler layer                      |
+---+---------+---+---+-----------------------------------------------+
|   | nofill  |   |   | GraphMetal1 filler exclusion layer            |
+---+---------+---+---+-----------------------------------------------+
|   | slit    |   |   | GraphMetal1 slit definition layer             |
+---+---------+---+---+-----------------------------------------------+
|   | OPC     |   |   | Graphene-metal opc                            |
+---+---------+---+---+-----------------------------------------------+
|   | drawing |   |   | Graphene-metal lift-off interconnect          |
+---+---------+---+---+-----------------------------------------------+
|   | filler  |   |   | GraphMet1L filler layer                       |
+---+---------+---+---+-----------------------------------------------+
|   | nofill  |   |   | GraphMet1L filler exclusion layer             |
+---+---------+---+---+-----------------------------------------------+
|   | slit    |   |   | GraphMet1L slit definition layer              |
+---+---------+---+---+-----------------------------------------------+
|   | OPC     |   |   | Graphene-metal lift-off opc                   |
+---+---------+---+---+-----------------------------------------------+
|   | drawing |   |   | Block tip and halo implants                   |
+---+---------+---+---+-----------------------------------------------+
|   | drawing |   |   | Dedicated pwell body for NLDMOS               |
+---+---------+---+---+-----------------------------------------------+
|   | drawing |   |   | Dedicated nwell body for PLDMOS               |
+---+---------+---+---+-----------------------------------------------+
|   | drawing |   |   | Reserved for internal LDMOS development       |
+---+---------+---+---+-----------------------------------------------+
|   | drawing |   |   | Reserved for internal use                     |
+---+---------+---+---+-----------------------------------------------+
|   | drawing |   |   | Reserved for internal use                     |
+---+---------+---+---+-----------------------------------------------+
|   | drawing |   |   | Reserved for internal use                     |
+---+---------+---+---+-----------------------------------------------+
|   | drawing |   |   | Graphene GFET gate                            |
+---+---------+---+---+-----------------------------------------------+
|   | drawing |   |   | Backend integrated SiN waveguide              |
+---+---------+---+---+-----------------------------------------------+
|   | filler  |   |   | SiNWG filler layer                            |
+---+---------+---+---+-----------------------------------------------+
|   | nofill  |   |   | SiNWG filler exclusion layer                  |
+---+---------+---+---+-----------------------------------------------+
|   | drawing |   |   | Dedicated to open Pads in RF-MEMS module      |
+---+---------+---+---+-----------------------------------------------+
|   | drawing |   |   | Defines 3-rd (or 5-th) metal to TopMetal1     |
|   |         |   |   | contact                                       |
+---+---------+---+---+-----------------------------------------------+
|   | drawing |   |   | Defines 1-st thick TopMetal layer             |
+---+---------+---+---+-----------------------------------------------+
|   | pin     |   |   | TopMetal1 pin layer                           |
+---+---------+---+---+-----------------------------------------------+
|   | mask    |   |   | added to TopMetal1:drawing at mask generation |
+---+---------+---+---+-----------------------------------------------+
|   | filler  |   |   | TopMetal1 filler layer                        |
+---+---------+---+---+-----------------------------------------------+
|   | nofill  |   |   | TopMetal1 filler exclusion layer              |
+---+---------+---+---+-----------------------------------------------+
|   | slit    |   |   | TopMetal1 slit definition layer               |
+---+---------+---+---+-----------------------------------------------+
|   | text    |   |   | Text layer for TopMetal1, used for LVS        |
+---+---------+---+---+-----------------------------------------------+
|   | noqrc   |   |   | No parasitics extraction                      |
+---+---------+---+---+-----------------------------------------------+
|   | res     |   |   | Wire resistor                                 |
+---+---------+---+---+-----------------------------------------------+
|   | iprobe  |   |   | Current probe                                 |
+---+---------+---+---+-----------------------------------------------+
|   | diffprb |   |   | Differential current probe                    |
+---+---------+---+---+-----------------------------------------------+
|   | drawing |   |   | Dedicated PWell body for isolated NLDMOS      |
+---+---------+---+---+-----------------------------------------------+
|   | drawing |   |   | used to mark net resistors                    |
+---+---------+---+---+-----------------------------------------------+
|   | pin     |   |   | Defines polysilicon gates and interconnect    |
+---+---------+---+---+-----------------------------------------------+
|   | drawing |   |   | used to mark net mim capacitors               |
+---+---------+---+---+-----------------------------------------------+
|   | drawing |   |   | P-separation implat INLDMOS (internal use)    |
+---+---------+---+---+-----------------------------------------------+
|   | drawing |   |   | Extra first-metal layer for antenna and       |
|   |         |   |   | passive integration                           |
+---+---------+---+---+-----------------------------------------------+
|   | drawing |   |   | Defines via between TopMetal1 and TopMetal2   |
+---+---------+---+---+-----------------------------------------------+
|   | drawing |   |   | Defines 2-nd thick TopMetal layer             |
+---+---------+---+---+-----------------------------------------------+
|   | pin     |   |   | TopMetal2 pin layer                           |
+---+---------+---+---+-----------------------------------------------+
|   | mask    |   |   | added to TopMetal2:drawing at mask generation |
+---+---------+---+---+-----------------------------------------------+
|   | filler  |   |   | TopMetal2 filler layer                        |
+---+---------+---+---+-----------------------------------------------+
|   | nofill  |   |   | TopMetal2 filler exclusion layer              |
+---+---------+---+---+-----------------------------------------------+
|   | slit    |   |   | TopMetal2 slit definition layer               |
+---+---------+---+---+-----------------------------------------------+
|   | text    |   |   | Text layer for TopMetal2                      |
+---+---------+---+---+-----------------------------------------------+
|   | noqrc   |   |   | No parasitics extraction                      |
+---+---------+---+---+-----------------------------------------------+
|   | res     |   |   | Wire resistor                                 |
+---+---------+---+---+-----------------------------------------------+
|   | iprobe  |   |   | Current probe                                 |
+---+---------+---+---+-----------------------------------------------+
|   | diffprb |   |   | Differential current probe                    |
+---+---------+---+---+-----------------------------------------------+
|   | drawing |   |   | Sensor package ring                           |
+---+---------+---+---+-----------------------------------------------+
|   | drawing |   |   | Sensor recognition layer                      |
+---+---------+---+---+-----------------------------------------------+
|   | drawing |   |   | Arms of the Sensor                            |
+---+---------+---+---+-----------------------------------------------+
|   | drawing |   |   | Defines via between BiCMOS wafer and sensor   |
+---+---------+---+---+-----------------------------------------------+
|   | drawing |   |   | Defines enclosed active transistor region     |
+---+---------+---+---+-----------------------------------------------+
|   | drawing |   |   | Defines fluidic channel                       |
+---+---------+---+---+-----------------------------------------------+
|   | drawing |   |   | MEMRES dielectric layer                       |
+---+---------+---+---+-----------------------------------------------+
|   | drawing |   |   | Local Vias within RFM area                    |
+---+---------+---+---+-----------------------------------------------+
|   | drawing |   |   | ThinFilmRes (V) and recognition layer for     |
|   |         |   |   | RFMEMS                                        |
+---+---------+---+---+-----------------------------------------------+
|   | drawing |   |   | Areas for integrated RF MEMS devices          |
+---+---------+---+---+-----------------------------------------------+
|   | drawing |   |   | No parasitics extraction                      |
+---+---------+---+---+-----------------------------------------------+
|   | m2m3    |   |   | No parasitics extraction in Metal2 and Metal3 |
+---+---------+---+---+-----------------------------------------------+
|   | m2m4    |   |   | No parasitics extraction in Metal2 and Metal4 |
+---+---------+---+---+-----------------------------------------------+
|   | m2m5    |   |   | No parasitics extraction in Metal2 and Metal5 |
+---+---------+---+---+-----------------------------------------------+
|   | m2tm1   |   |   | No parasitics extraction in Metal2 and        |
|   |         |   |   | TopMetal1                                     |
+---+---------+---+---+-----------------------------------------------+
|   | m2tm2   |   |   | No parasitics extraction in Metal2 and        |
|   |         |   |   | TopMetal2                                     |
+---+---------+---+---+-----------------------------------------------+
|   | m3m4    |   |   | No parasitics extraction in Metal3 and Metal4 |
+---+---------+---+---+-----------------------------------------------+
|   | m3m5    |   |   | No parasitics extraction in Metal3 and Metal5 |
+---+---------+---+---+-----------------------------------------------+
|   | m3tm1   |   |   | No parasitics extraction in Metal3 and        |
|   |         |   |   | TopMetal1                                     |
+---+---------+---+---+-----------------------------------------------+
|   | m3tm2   |   |   | No parasitics extraction in Metal3 and        |
|   |         |   |   | TopMetal2                                     |
+---+---------+---+---+-----------------------------------------------+
|   | m4m5    |   |   | No parasitics extraction in Metal4 and Metal5 |
+---+---------+---+---+-----------------------------------------------+
|   | m4tm1   |   |   | No parasitics extraction in Metal4 and        |
|   |         |   |   | TopMetal1                                     |
+---+---------+---+---+-----------------------------------------------+
|   | m4tm2   |   |   | No parasitics extraction in Metal4 and        |
|   |         |   |   | TopMetal2                                     |
+---+---------+---+---+-----------------------------------------------+
|   | m5tm1   |   |   | No parasitics extraction in Metal5 and        |
|   |         |   |   | TopMetal1                                     |
+---+---------+---+---+-----------------------------------------------+
|   | m5tm2   |   |   | No parasitics extraction in Metal5 and        |
|   |         |   |   | TopMetal2                                     |
+---+---------+---+---+-----------------------------------------------+
|   | tm1tm2  |   |   | No parasitics extraction in TopMetal1 and     |
|   |         |   |   | TopMetal2                                     |
+---+---------+---+---+-----------------------------------------------+
|   | m1sub   |   |   | No parasitics extraction in Metal1 and        |
|   |         |   |   | Substrate                                     |
+---+---------+---+---+-----------------------------------------------+
|   | m2sub   |   |   | No parasitics extraction in Metal2 and        |
|   |         |   |   | Substrate                                     |
+---+---------+---+---+-----------------------------------------------+
|   | m3sub   |   |   | No parasitics extraction in Metal3 and        |
|   |         |   |   | Substrate                                     |
+---+---------+---+---+-----------------------------------------------+
|   | m4sub   |   |   | No parasitics extraction in Metal4 and        |
|   |         |   |   | Substrate                                     |
+---+---------+---+---+-----------------------------------------------+
|   | m5sub   |   |   | No parasitics extraction in Metal5 and        |
|   |         |   |   | Substrate                                     |
+---+---------+---+---+-----------------------------------------------+
|   | tm1sub  |   |   | No parasitics extraction in TopMetal1 and     |
|   |         |   |   | Substrate                                     |
+---+---------+---+---+-----------------------------------------------+
|   | tm2sub  |   |   | No parasitics extraction in TopMetal2 and     |
|   |         |   |   | Substrate                                     |
+---+---------+---+---+-----------------------------------------------+
|   | drawing |   |   | Sensor bottom via                             |
+---+---------+---+---+-----------------------------------------------+
|   | drawing |   |   | Sensor top via                                |
+---+---------+---+---+-----------------------------------------------+
|   | drawing |   |   | Through Silicon Via                           |
+---+---------+---+---+-----------------------------------------------+
|   | drawing |   |   | At this place the 1-st poly-Si layer          |
|   |         |   |   | (floating-gate) is etched before the 2-nd     |
|   |         |   |   | poly-Si layer (control-gate) is deposited     |
+---+---------+---+---+-----------------------------------------------+
|   | drawing |   |   | This layer patterns the 2-nd poly-Si layer    |
|   |         |   |   | (control-gate)                                |
+---+---------+---+---+-----------------------------------------------+
|   | drawing |   |   | Defines areas where the Floating-gate is      |
|   |         |   |   | doped and the p-well of the flash-cells is    |
|   |         |   |   | formed                                        |
+---+---------+---+---+-----------------------------------------------+
|   | drawing |   |   | EmWind layer for high voltage HBT             |
+---+---------+---+---+-----------------------------------------------+
|   | drawing |   |   | For localized back side etch                  |
+---+---------+---+---+-----------------------------------------------+
|   | drawing |   |   | Reserved for internal use                     |
+---+---------+---+---+-----------------------------------------------+
|   | drawing |   |   | Exclude all metall filler                     |
+---+---------+---+---+-----------------------------------------------+
|   | drawing |   |   | Defines boundary of layour cells              |
+---+---------+---+---+-----------------------------------------------+
|   | drawing |   |   | Support layer for layout data exchange (not   |
|   |         |   |   | used in mask preparation)                     |
+---+---------+---+---+-----------------------------------------------+
|   | pin     |   |   | Pin layer of Exchange0                        |
+---+---------+---+---+-----------------------------------------------+
|   | text    |   |   | Text layer of Exchange0                       |
+---+---------+---+---+-----------------------------------------------+
|   | drawing |   |   | Support layer for layout data exchange (not   |
|   |         |   |   | used in mask preparation)                     |
+---+---------+---+---+-----------------------------------------------+
|   | pin     |   |   | Pin layer of Exchange1                        |
+---+---------+---+---+-----------------------------------------------+
|   | text    |   |   | Text layer of Exchange1                       |
+---+---------+---+---+-----------------------------------------------+
|   | drawing |   |   | Support layer for layout data exchange (not   |
|   |         |   |   | used in mask preparation)                     |
+---+---------+---+---+-----------------------------------------------+
|   | pin     |   |   | Pin layer of Exchange2                        |
+---+---------+---+---+-----------------------------------------------+
|   | text    |   |   | Text layer of Exchange2                       |
+---+---------+---+---+-----------------------------------------------+
|   | drawing |   |   | Support layer for layout data exchange (not   |
|   |         |   |   | used in mask preparation)                     |
+---+---------+---+---+-----------------------------------------------+
|   | pin     |   |   | Pin layer of Exchange3                        |
+---+---------+---+---+-----------------------------------------------+
|   | text    |   |   | Text layer of Exchange3                       |
+---+---------+---+---+-----------------------------------------------+
|   | drawing |   |   | Support layer for layout data exchange (not   |
|   |         |   |   | used in mask preparation)                     |
+---+---------+---+---+-----------------------------------------------+
|   | pin     |   |   | Pin layer of Exchange4                        |
+---+---------+---+---+-----------------------------------------------+
|   | text    |   |   | Text layer of Exchange4                       |
+---+---------+---+---+-----------------------------------------------+
|   | drawing |   |   | Defines regions with alternative NWell        |
|   |         |   |   | implant to form isolated NWell                |
+---+---------+---+---+-----------------------------------------------+

.. _`c:general`:

General Requirements
====================

.. _`s:grid`:

Grid Rules
----------

-  All rules are defined in microns [µm] by default if there is no other
   unit mentioned

-  All features are on a drawing grid of 5 nm (0.005 µm)

-  Shapes with acute angles <87° are not allowed on any layer

-  Following layers are only allowed on 90, 180 degree angles: Cont,
   Via1, Via2, Via3, Via4, Vmim, TopVia1, TopVia2

-  Following layers are only allowed on 90, 135, 180, 225, and 270
   degree angles: GatPoly, Activ, Metal1, Metal2, Metal3, Metal4,
   Metal5, TopMetal1, TopMetal2

-  Self-intersecting polygons must be avoided

-  Design elements, which are snapped to grid must not violate any
   geometries in this document.

There are several layers which are not considered for mask generation.
Offgrid and angle checks are not applied on the following layers:
DigiBnd, RES, SRAM, IND, EdgeSeal, dfpad, HeatTrans, HeatRes, DigiSub,
NoDRC, TEXT, RadHard, Flash, SMOS, Scribe, Recog, NoRCX, NoMetFiller

.. _`s:forbidden-layers`:

Forbidden Layers
----------------

Following layers are forbidden in designs submitted for all 0.13 µm
technologies. Layout data containing these layers will be rejected from
the tape-in procedure automatically. Since no waivers are granted, IHP
recommends performing the online `MPW Rejection Test
(https://dk.ihp-microelectronics.com) <https://dk.ihp-microelectronics.com>`__
at an early stage.

== =======
\  drawing  
\  drawing  
\  drawing  
\  drawing  
\  drawing  
\  drawing  
\  drawing  
\  drawing  
\  drawing  
\  drawing  
\  drawing  
== =======

.. _`c:terminology`:

Terminology
===========

Design Rule Terminology
-----------------------

| **unrelated** - two regions which do not touch each other
| **abut** - two edges of two different layers touching each other

.. figure:: common/img/pdf/design_rule_terminology.pdf
   name: f:dr_terminology

   Rule check schematics.

.. _`s:special_layers`:

Special Layer Configuration
---------------------------

Various rule definitions require derived layers instead of the original
layers defined in chapter `2 <#c:layertable>`__. The generation rules
for the derived layers are described below.

===== =================================================
\     NOT ( OR ) OR
 [1]_ NOT ( OR ) OR
\     ((( ≥ 3.0 µm) sized by -1.0 µm/side) OR ) AND NOT
\     ( AND ) inside
\     ( AND ) inside
\     AND
\     AND
\     AND
\     over ( AND NOT )
\     over (( AND ) inside )
===== =================================================

Physical Layer Design Rules
===========================

.. _`s:nwell`:

NWell
-----

.. container:: tabular

   \|>

   p2.4cm\|>

   p10.5cm\|>p1.8cm\|

   | & &

   | NW.a & Min. width &
   | NW.a & Min. width & &

   | NW.b & Min. space or notch (same net). regions separated by less
     than this value will be merged. &
   | NW.b & Min. space or notch (same net). regions separated by less
     than this value will be merged. & &

   | NW.b1 & Min. width between regions (different net) (Note
     `[nwell_n3] <#nwell_n3>`__) &
   | NW.b1 & Min. width between regions (different net) (Note
     `[nwell_n3] <#nwell_n3>`__) & &

   | NW.c & Min. enclosure of not inside &
   | NW.c & Min. enclosure of not inside & &

   | NW.c1 & Min. enclosure of inside &
   | NW.c1 & Min. enclosure of inside & &

   | NW.d & Min. space to external not inside &
   | NW.d & Min. space to external not inside & &

   | NW.d1 & Min. space to external inside &
   | NW.d1 & Min. space to external inside & &

   | NW.e & Min. enclosure of NWell tie surrounded entirely by in not
     inside &
   | NW.e & Min. enclosure of NWell tie surrounded entirely by in not
     inside & &

   | NW.e1 & Min. enclosure of NWell tie surrounded entirely by in
     inside &
   | NW.e1 & Min. enclosure of NWell tie surrounded entirely by in
     inside & &

   | NW.f & Min. space to substrate tie in not inside &
   | NW.f & Min. space to substrate tie in not inside & &

   | NW.f1 & Min. space to substrate tie in inside &
   | NW.f1 & Min. space to substrate tie in inside & &

Notes
~~~~~

#. regions are allowed to cross well boundaries in some ESD protection
   layouts.

#. Substrate ties for internal logic are required due to p-silicon
   substrate.

#. A certain distance between and (see section
   `4.2 <#s:special_layers>`__) on different nets is required to prevent
   punchthrough due to different potentials.

 

.. figure:: sg13/img/pdf/nwell.pdf

   dimensions (only rule variants without are shown in this figure)

.. _`s:pwellblock`:

PWell:block
-----------

layer is used to generate regions where both and implants are blocked.

.. container:: tabular

   \|>

   p2.4cm\|>

   p10.5cm\|>p1.8cm\|

   | & &

   | PWB.a & Min. width &
   | PWB.a & Min. width & &

   | PWB.b & Min. space or notch &
   | PWB.b & Min. space or notch & &

   | PWB.c & Min. space to unrelated &
   | PWB.c & Min. space to unrelated & &

   | PWB.d & Min. overlap of &
   | PWB.d & Min. overlap of & &

   | PWB.e & Min. space to ( not inside ) in &
   | PWB.e & Min. space to ( not inside ) in & &

   | PWB.e1 & Min. space to ( inside ) in &
   | PWB.e1 & Min. space to ( inside ) in & &

   | PWB.f & Min. space to ( not inside ) in &
   | PWB.f & Min. space to ( not inside ) in & &

   | PWB.f1 & Min. space to ( inside ) in &
   | PWB.f1 & Min. space to ( inside ) in & &

.. figure:: sg13/img/pdf/pwell_block.pdf

   dimensions

.. _`s:nbulay`:

nBuLay
------

defines regions with deep n-implants (deep nwell). This allows isolated
nmos devices to be realized. Furthermore, may be generated automatically
within (see `4.2 <#s:special_layers>`__) in order to reduce the
resistance of the .

.. container:: tabular

   \|>

   p2.4cm\|>

   p10.5cm\|>p1.8cm\|

   | & &

   | NBL.a & Min. width &
   | NBL.a & Min. width & &

   | NBL.b & Min. space or notch (same net) &
   | NBL.b & Min. space or notch (same net) & &

   | NBL.c & Min. width between regions (different net) (Note
     `[nbulay_n1] <#nbulay_n1>`__) &
   | NBL.c & Min. width between regions (different net) (Note
     `[nbulay_n1] <#nbulay_n1>`__) & &

   | NBL.d & Min. width between and (different net)
     (Note `[nbulay_n1] <#nbulay_n1>`__) &
   | NBL.d & Min. width between and (different net)
     (Note `[nbulay_n1] <#nbulay_n1>`__) & &

   | NBL.e & Min. space to unrelated &
   | NBL.e & Min. space to unrelated & &

   | NBL.f & Min. space to unrelated &
   | NBL.f & Min. space to unrelated & &

.. _notes-1:

Notes
~~~~~

#. A certain space to and on different nets is required to prevent
   punchthrough due to different potentials. Please note that drawn as
   well as generated regions are considered (see
   `4.2 <#s:special_layers>`__).

.. figure:: sg13/img/pdf/nbulay.pdf

   dimensions

.. _`s:nblb`:

nBuLay:block
------------

is used for generating structures, which are prevented from implant.
Latchup prevention has to be carefully considered whenever layer is used
(see `7.2 <#s:latchup>`__).

.. container:: tabular

   \|>

   p2.4cm\|>

   p10.5cm\|>p1.8cm\|

   | & &

   | NBL.a & Min. width &
   | NBL.a & Min. width & &

   | NBL.b & Min. space or notch &
   | NBL.b & Min. space or notch & &

   | NBL.c & Min. enclosure of &
   | NBL.c & Min. enclosure of & &

   | NBL.d & Min. space to unrelated &
   | NBL.d & Min. space to unrelated & &

.. figure:: sg13/img/pdf/nbulay_block.pdf

   dimensions

.. _`s:activ`:

Activ
-----

.. container:: tabular

   \|>

   p2.4cm\|>

   p10.5cm\|>p1.8cm\|

   | & &

   | Act.a & Min. width &
   | Act.a & Min. width & &

   | Act.b & Min. space or notch &
   | Act.b & Min. space or notch & &

   | Act.c & Min. drain/source extension &
   | Act.c & Min. drain/source extension & &

   | Act.d & Min. area (µm²) &
   | Act.d & Min. area (µm²) & &

   | Act.e & Min. enclosed area (µm²) &
   | Act.e & Min. enclosed area (µm²) & &

.. figure:: sg13/img/pdf/activ.pdf

   dimensions

.. _`s:actfiller`:

Activ:filler
------------

pattern are required in order to reduce layout sensitivity due to
etching and CMP process steps.

.. container:: tabular

   \|>

   p2.4cm\|>

   p10.5cm\|>p1.8cm\|

   | & &

   | AFil.a & Max. width &
   | AFil.a & Max. width & &

   | AFil.a1 & Min. width &
   | AFil.a1 & Min. width & &

   | AFil.b & Min. space &
   | AFil.b & Min. space & &

   | AFil.c & Min. space to , &
   | AFil.c & Min. space to , & &

   | AFil.c1 & Min. space to &
   | AFil.c1 & Min. space to & &

   | AFil.d & Min. space to , &
   | AFil.d & Min. space to , & &

   | AFil.e & Min. space to &
   | AFil.e & Min. space to & &

   | AFil.g & Min. global density [%] &
   | AFil.g & Min. global density [%] & &

   | AFil.g1 & Max. global density [%] &
   | AFil.g1 & Max. global density [%] & &

   | AFil.g2 & Min. coverage ratio for any 800 x 800 µm² chip area [%] &
   | AFil.g2 & Min. coverage ratio for any 800 x 800 µm² chip area [%] &
     &

   | AFil.g3 & Max. coverage ratio for any 800 x 800 µm² chip area [%] &
   | AFil.g3 & Max. coverage ratio for any 800 x 800 µm² chip area [%] &
     &

   | AFil.i & Min. space to edges of &
   | AFil.i & Min. space to edges of & &

   | AFil.j & Min. and enclosure of inside &
   | AFil.j & Min. and enclosure of inside & &

.. _notes-2:

Notes
~~~~~

#. layer can be used for filler pattern exclusion within specific device
   areas such as inductors or transformers as long as AFil.g2 and
   AFil.g3 are fulfilled. For larger sensitive areas it is recommended
   to minimize the conductivity of patterns by using , and .

.. figure:: sg13/img/pdf/activ_filler.pdf

   dimensions

.. _`s:tgo`:

ThickGateOxide
--------------

.. container:: tabular

   \|>

   p2.4cm\|>

   p10.5cm\|>p1.8cm\|

   | & &

   | TGO.a & Min. extension over &
   | TGO.a & Min. extension over & &

   | TGO.b & Min. space between and outside thick gate oxide region &
   | TGO.b & Min. space between and outside thick gate oxide region & &

   | TGO.c & Min. extension over over &
   | TGO.c & Min. extension over over & &

   | TGO.d & Min. space between and over outside thick gate oxide region
     &
   | TGO.d & Min. space between and over outside thick gate oxide region
     & &

   | TGO.e & Min. space (merge if less than this value) &
   | TGO.e & Min. space (merge if less than this value) & &

   | TGO.f & Min. width &
   | TGO.f & Min. width & &

.. figure:: sg13/img/pdf/thickgateox.pdf

   dimensions

.. _`s:gatpoly`:

GatPoly
-------

.. container:: tabular

   \|>

   p2.4cm\|>

   p10.5cm\|>p1.8cm\|

   | & &

   | Gat.a & Min. width &
   | Gat.a & Min. width & &

   | Gat.a1 & Min. width for channel length of 1.2 V NFET &
   | Gat.a1 & Min. width for channel length of 1.2 V NFET & &

   | Gat.a2 & Min. width for channel length of 1.2 V PFET &
   | Gat.a2 & Min. width for channel length of 1.2 V PFET & &

   | Gat.a3 & Min. width for channel length of 3.3 V NFET &
   | Gat.a3 & Min. width for channel length of 3.3 V NFET & &

   | Gat.a4 & Min. width for channel length of 3.3 V PFET &
   | Gat.a4 & Min. width for channel length of 3.3 V PFET & &

   | Gat.b & Min. space or notch &
   | Gat.b & Min. space or notch & &

   | Gat.b1 & Min. space between unrelated 3.3 V over regions &
   | Gat.b1 & Min. space between unrelated 3.3 V over regions & &

   | Gat.c & Min. extension over (end cap) &
   | Gat.c & Min. extension over (end cap) & &

   | Gat.d & Min. space to &
   | Gat.d & Min. space to & &

   | Gat.e & Min. area (µm²) &
   | Gat.e & Min. area (µm²) & &

   | Gat.f & 45-degree and 90-degree angles for on area are not allowed
     &
   | Gat.f & 45-degree and 90-degree angles for on area are not allowed
     & &

   | Gat.g & Min. width for 45-degree bent shapes if the bend length is
     > 0.39 µm &
   | Gat.g & Min. width for 45-degree bent shapes if the bend length is
     > 0.39 µm & &

.. figure:: sg13/img/pdf/gatpoly.pdf

   dimensions

.. _`s:gatfiller`:

GatPoly:filler
--------------

pattern are required in order to reduce layout sensitivity due to
etching and CMP process steps.

.. container:: tabular

   \|>

   p2.4cm\|>

   p10.5cm\|>p1.8cm\|

   | & &

   | GFil.a & Max. width &
   | GFil.a & Max. width & &

   | GFil.b & Min. width &
   | GFil.b & Min. width & &

   | GFil.c & Min. space &
   | GFil.c & Min. space & &

   | GFil.d & Min. space to , , , , , &
   | GFil.d & Min. space to , , , , , & &

   | GFil.e & Min. space to , &
   | GFil.e & Min. space to , & &

   | GFil.f & Min. space to &
   | GFil.f & Min. space to & &

   | GFil.g & Min. global density [%] &
   | GFil.g & Min. global density [%] & &

   | GFil.i & Max. area (µm²) &
   | GFil.i & Max. area (µm²) & &

   | GFil.j & Min. extension over (end cap) &
   | GFil.j & Min. extension over (end cap) & &

.. _notes-3:

Notes
~~~~~

#. layer can be used for filler pattern exclusion within specific device
   areas such as inductors or transformers.

.. figure:: sg13/img/pdf/gatpoly_filler.pdf

   dimensions

.. _`s:psd`:

pSD
---

Defines regions which receive p+ implants. Typically used for
source/drain implants, resistors and substrate ties.

.. container:: tabular

   \|>

   p2.4cm\|>

   p10.5cm\|>p1.8cm\|

   | & &

   | pSD.a & Min. width &
   | pSD.a & Min. width & &

   | pSD.b & Min. space or notch (Note `[psd_n1] <#psd_n1>`__) &
   | pSD.b & Min. space or notch (Note `[psd_n1] <#psd_n1>`__) & &

   | pSD.c & Min. enclosure of in &
   | pSD.c & Min. enclosure of in & &

   | pSD.c1 & Min. enclosure of in &
   | pSD.c1 & Min. enclosure of in & &

   | pSD.d & Min. space to unrelated in &
   | pSD.d & Min. space to unrelated in & &

   | pSD.d1 & Min. space to in &
   | pSD.d1 & Min. space to in & &

   | pSD.e & Min. overlap of at one position when forming abutted
     substrate tie (Note `[psd_n2] <#psd_n2>`__) &
   | pSD.e & Min. overlap of at one position when forming abutted
     substrate tie (Note `[psd_n2] <#psd_n2>`__) & &

   | pSD.f & Min. extension over at one position when forming abutted
     tie (Note `[psd_n2] <#psd_n2>`__) &
   | pSD.f & Min. extension over at one position when forming abutted
     tie (Note `[psd_n2] <#psd_n2>`__) & &

   | pSD.g & Min. or area (µm²) when forming abutted tie (Note
     `[psd_n2] <#psd_n2>`__) &
   | pSD.g & Min. or area (µm²) when forming abutted tie (Note
     `[psd_n2] <#psd_n2>`__) & &

   | pSD.i & Min. enclosure of PFET gate (thin gate oxide) &
   | pSD.i & Min. enclosure of PFET gate (thin gate oxide) & &

   | pSD.i1 & Min. enclosure of PFET gate (thick gate oxide) &
   | pSD.i1 & Min. enclosure of PFET gate (thick gate oxide) & &

   | pSD.j & Min. enclosure of NFET gate (thin gate oxide) &
   | pSD.j & Min. enclosure of NFET gate (thin gate oxide) & &

   | pSD.j1 & Min. enclosure of NFET gate (thick gate oxide) &
   | pSD.j1 & Min. enclosure of NFET gate (thick gate oxide) & &

   | pSD.k & Min. area (µm²) &
   | pSD.k & Min. area (µm²) & &

   | pSD.l & Min. enclosed area (µm²) &
   | pSD.l & Min. enclosed area (µm²) & &

   | pSD.m & Min. space to n-type poly resistors &
   | pSD.m & Min. space to n-type poly resistors & &

   | pSD.n & Min. enclosure of p-type poly resistors &
   | pSD.n & Min. enclosure of p-type poly resistors & &

.. _notes-4:

Notes
~~~~~

#. regions separated by less than this value will be merged.

#. These rules are for abutted ties: An electrical connection from
   P+Activ to NWell tie (or N+ Activ to P-sub tie) is made through the
   source/drain silicide. For a good electrical connection rule pSD.g is
   important together with rule pSD.e or pSD.f (see Fig.
   `5.1 <#fig:psd>`__).

 

.. figure:: sg13/img/pdf/psd.pdf
   name: fig:psd

   dimensions

.. _`s:nsdb`:

nSD:block
---------

layer is used to generate regions where n+ S/D implants are blocked. The
final mask data are generated by: nSD: = NOT (pSD OR nSD:block).

.. container:: tabular

   \|>

   p2.4cm\|>

   p10.5cm\|>p1.8cm\|

   | & &

   | nSDB.a & Min. width &
   | nSDB.a & Min. width & &

   | nSDB.b & Min. space or notch &
   | nSDB.b & Min. space or notch & &

   | nSDB.c & Min. space to unrelated &
   | nSDB.c & Min. space to unrelated & &

   | nSDB.d & Min. overlap of (Note `[nsdb_n1] <#nsdb_n1>`__) &
   | nSDB.d & Min. overlap of (Note `[nsdb_n1] <#nsdb_n1>`__) & &

   | nSDB.e & Min. space to (Note `[nsdb_n2] <#nsdb_n2>`__) &
   | nSDB.e & Min. space to (Note `[nsdb_n2] <#nsdb_n2>`__) & &

.. _notes-5:

Notes
~~~~~

#. and are allowed to overlap or to be line-on-line.

#. and do not overlap.

.. figure:: sg13/img/pdf/nbulay_block.pdf

   dimensions

.. _`s:ext`:

EXTBlock
--------

layer is used to generate regions where all tip and halo implants are
blocked.

.. container:: tabular

   \|>

   p2.4cm\|>

   p10.5cm\|>p1.8cm\|

   | & &

   | EXT.a & Min. width &
   | EXT.a & Min. width & &

   | EXT.b & Min. space or notch &
   | EXT.b & Min. space or notch & &

   | EXT.c & Min. space to &
   | EXT.c & Min. space to & &

.. figure:: sg13/img/pdf/extblock.pdf

   dimensions

.. _`s:sal`:

SalBlock
--------

is used to block salicidation of or source/drain areas.

.. container:: tabular

   \|>

   p2.4cm\|>

   p10.5cm\|>p1.8cm\|

   | & &

   | Sal.a & Min. width &
   | Sal.a & Min. width & &

   | Sal.b & Min. space or notch &
   | Sal.b & Min. space or notch & &

   | Sal.c & Min. extension over or &
   | Sal.c & Min. extension over or & &

   | Sal.d & Min. space to unrelated or &
   | Sal.d & Min. space to unrelated or & &

   | Sal.d & Min. space to &
   | Sal.d & Min. space to & &

.. figure:: sg13/img/pdf/salblock.pdf

   dimensions

.. _`s:cnt`:

Cont
----

This section describes design rules for square-shaped regions. All
non-square shapes in layer are covered in section `5.15 <#s:cntb>`__.

.. container:: tabular

   \|>

   p2.4cm\|>

   p10.5cm\|>p1.8cm\|

   | & &

   | Cnt.a & Min. and max. width &
   | Cnt.a & Min. and max. width & &

   | Cnt.b & Min. space &
   | Cnt.b & Min. space & &

   | Cnt.b1 & Min. space in a contact array of more than 4 rows and more
     then 4 columns (Note `[cnt_n1] <#cnt_n1>`__) &
   | Cnt.b1 & Min. space in a contact array of more than 4 rows and more
     then 4 columns (Note `[cnt_n1] <#cnt_n1>`__) & &

   | Cnt.c & Min. enclosure of &
   | Cnt.c & Min. enclosure of & &

   | Cnt.d & Min. enclosure of &
   | Cnt.d & Min. enclosure of & &

   | Cnt.e & Min. on space to &
   | Cnt.e & Min. on space to & &

   | Cnt.f & Min. on space to &
   | Cnt.f & Min. on space to & &

   | Cnt.g & must be within or &
   | Cnt.g & must be within or & &

   | Cnt.g1 & Min. space to on &
   | Cnt.g1 & Min. space to on & &

   | Cnt.g2 & Min. overlap of on &
   | Cnt.g2 & Min. overlap of on & &

   | Cnt.h & must be covered with &
   | Cnt.h & must be covered with & &

   | Cnt.j & on over is not allowed &
   | Cnt.j & on over is not allowed & &

.. _notes-6:

Notes
~~~~~

#. Cnt.b1 is only required in one direction. The distance of the other
   direction must be at least Cnt.b.

.. figure:: sg13/img/pdf/cont.pdf

   dimensions

.. _`s:cntb`:

ContBar
-------

Any shape not being a square shape is considered a .

.. container:: tabular

   \|>

   p2.4cm\|>

   p10.5cm\|>p1.8cm\|

   | & &

   | CntB.a & Min. and max. width &
   | CntB.a & Min. and max. width & &

   | CntB.a1 & Min. length &
   | CntB.a1 & Min. length & &

   | CntB.b & Min. space &
   | CntB.b & Min. space & &

   | CntB.b1 & Min. space with common run > 5 µm &
   | CntB.b1 & Min. space with common run > 5 µm & &

   | CntB.b2 & Min. space to &
   | CntB.b2 & Min. space to & &

   | CntB.c & Min. enclosure of &
   | CntB.c & Min. enclosure of & &

   | CntB.d & Min. enclosure of &
   | CntB.d & Min. enclosure of & &

   | CntB.e & Min. on space to &
   | CntB.e & Min. on space to & &

   | CntB.f & Min. on space to &
   | CntB.f & Min. on space to & &

   | CntB.g & must be within or &
   | CntB.g & must be within or & &

   | CntB.g1 & Min. space to on &
   | CntB.g1 & Min. space to on & &

   | CntB.g1 & Min. overlap of on &
   | CntB.g1 & Min. overlap of on & &

   | CntB.h & must be covered with &
   | CntB.h & must be covered with & &

   | CntB.h1 & Min. enclosure of &
   | CntB.h1 & Min. enclosure of & &

   | CntB.j & on over is not allowed &
   | CntB.j & on over is not allowed & &

.. figure:: sg13/img/pdf/contbar.pdf

   dimensions

.. _`s:m1`:

Metal1
------

.. container:: tabular

   \|>

   p2.4cm\|>

   p10.5cm\|>p1.8cm\|

   | & &

   | M1.a & Min. width &
   | M1.a & Min. width & &

   | M1.b & Min. space or notch &
   | M1.b & Min. space or notch & &

   | M1.c & Min. enclosure of &
   | M1.c & Min. enclosure of & &

   | M1.c1 & Min. endcap enclosure of (Note `[m1_n1] <#m1_n1>`__) &
   | M1.c1 & Min. endcap enclosure of (Note `[m1_n1] <#m1_n1>`__) & &

   | M1.d & Min. area (µm²) &
   | M1.d & Min. area (µm²) & &

   | M1.e & Min. space of lines if, at least one line is wider than 0.3
     µm and the parallel run is more than 1.0 µm &
   | M1.e & Min. space of lines if, at least one line is wider than 0.3
     µm and the parallel run is more than 1.0 µm & &

   | M1.f & Min. space of lines if, at least one line is wider than 10.0
     µm and the parallel run is more than 10.0 µm &
   | M1.f & Min. space of lines if, at least one line is wider than 10.0
     µm and the parallel run is more than 10.0 µm & &

   | M1.g & Min. 45-degree bent width if the bent metal length is > 0.5
     µm &
   | M1.g & Min. 45-degree bent width if the bent metal length is > 0.5
     µm & &

   | M1.i & Min. space of lines of which at least one is bent by
     45-degree &
   | M1.i & Min. space of lines of which at least one is bent by
     45-degree & &

   | M1.j & Min. global density [%] &
   | M1.j & Min. global density [%] & &

   | M1.k & Max. global density [%] &
   | M1.k & Max. global density [%] & &

.. _notes-7:

Notes
~~~~~

#. For contacts at corners at least one side must be treated as an
   endcap and for the other sides rule M1.c can be applied.

.. figure:: sg13/img/pdf/metal1.pdf

   dimensions

.. _`s:mn`:

Metal(n=2-5)
------------

.. container:: tabular

   \|>

   p2.4cm\|>

   p10.5cm\|>p1.8cm\|

   | & &

   | Mn.a & Min. width &
   | Mn.a & Min. width & &

   | Mn.b & Min. space or notch &
   | Mn.b & Min. space or notch & &

   | Mn.c & Min. enclosure of &
   | Mn.c & Min. enclosure of & &

   | Mn.c1 & Min. endcap enclosure of (Note `[mn_n1] <#mn_n1>`__) &
   | Mn.c1 & Min. endcap enclosure of (Note `[mn_n1] <#mn_n1>`__) & &

   | Mn.d & Min. area (µm²) &
   | Mn.d & Min. area (µm²) & &

   | Mn.e & Min. space of lines if, at least one line is wider than 0.39
     µm and the parallel run is more than 1.0 µm &
   | Mn.e & Min. space of lines if, at least one line is wider than 0.39
     µm and the parallel run is more than 1.0 µm & &

   | Mn.f & Min. space of lines if, at least one line is wider than 10.0
     µm and the parallel run is more than 10.0 µm &
   | Mn.f & Min. space of lines if, at least one line is wider than 10.0
     µm and the parallel run is more than 10.0 µm & &

   | Mn.g & Min. 45-degree bent width if the bent metal length is > 0.5
     µm &
   | Mn.g & Min. 45-degree bent width if the bent metal length is > 0.5
     µm & &

   | Mn.i & Min. space of lines of which at least one is bent by
     45-degree &
   | Mn.i & Min. space of lines of which at least one is bent by
     45-degree & &

   | Mn.j & Min. global density [%] &
   | Mn.j & Min. global density [%] & &

   | Mn.k & Max. global density [%] &
   | Mn.k & Max. global density [%] & &

.. _notes-8:

Notes
~~~~~

#. For vias at corners at least one side must be treated as an endcap
   and for the other sides rule Mn.c can be applied.

.. figure:: sg13/img/pdf/metaln.pdf

   dimensions

.. _`s:mfil`:

Metal(n=1-5):filler
-------------------

pattern are required in order to reduce layout sensitivity due to metal
etching and CMP process steps.

.. container:: tabular

   \|>

   p2.4cm\|>

   p10.5cm\|>p1.8cm\|

   | & &

   | MFil.a1 & Min. width &
   | MFil.a1 & Min. width & &

   | MFil.a2 & Max. width &
   | MFil.a2 & Max. width & &

   | MFil.b & Min. space &
   | MFil.b & Min. space & &

   | MFil.c & Min. space to &
   | MFil.c & Min. space to & &

   | MFil.d & Min. space to &
   | MFil.d & Min. space to & &

   | MFil.h & Min. and coverage ratio for any 800 x 800 µm² chip area
     [%] &
   | MFil.h & Min. and coverage ratio for any 800 x 800 µm² chip area
     [%] & &

   | MFil.k & Max. and coverage ratio for any 800 x 800 µm² chip area
     [%] &
   | MFil.k & Max. and coverage ratio for any 800 x 800 µm² chip area
     [%] & &

.. _notes-9:

Notes
~~~~~

#. A smaller coverage or larger filler exclusion area leads to smaller
   metal lines and higher sheet resistance. Sheet resistance of minimum
   width lines is increasing by 10% if metal coverage is lower than 30%.

#. must be generated prior to the tape out procedure. For sensitive
   areas of the circuit, designers should exclude using the or exclusion
   layer, or should place defined metal structures to prevent metal
   fill.

.. figure:: sg13/img/pdf/metaln_filler.pdf

   dimensions

.. _`s:v1`:

Via1
----

.. container:: tabular

   \|>

   p2.4cm\|>

   p10.5cm\|>p1.8cm\|

   | & &

   | V1.a & Min. and max. width &
   | V1.a & Min. and max. width & &

   | V1.b & Min. space &
   | V1.b & Min. space & &

   | V1.b1 & Min. space in an array of more than 3 rows and more then 3
     columns (Note `[v1_n1] <#v1_n1>`__) &
   | V1.b1 & Min. space in an array of more than 3 rows and more then 3
     columns (Note `[v1_n1] <#v1_n1>`__) & &

   | V1.c & Min. enclosure of &
   | V1.c & Min. enclosure of & &

   | V1.c1 & Min. endcap enclosure of (Note `[v1_n2] <#v1_n2>`__) &
   | V1.c1 & Min. endcap enclosure of (Note `[v1_n2] <#v1_n2>`__) & &

.. _notes-10:

Notes
~~~~~

#. V1.b1 is only required in one direction. The distance of the other
   direction must be at least V1.b.

#. For at corners at least one side must be treated as an endcap and for
   the other sides rule V1.c can be applied.

.. figure:: sg13/img/pdf/via1.pdf

   dimensions

.. _`s:vn`:

Via(n=2-4)
----------

.. container:: tabular

   \|>

   p2.4cm\|>

   p10.5cm\|>p1.8cm\|

   | & &

   | Vn.a & Min. and max. width &
   | Vn.a & Min. and max. width & &

   | Vn.b & Min. space &
   | Vn.b & Min. space & &

   | Vn.b1 & Min. space in an array of more than 3 rows and more then 3
     columns (Note `[v1_n1] <#v1_n1>`__) &
   | Vn.b1 & Min. space in an array of more than 3 rows and more then 3
     columns (Note `[v1_n1] <#v1_n1>`__) & &

   | Vn.c & Min. enclosure of &
   | Vn.c & Min. enclosure of & &

   | Vn.c1 & Min. endcap enclosure of (Note `[v1_n2] <#v1_n2>`__) &
   | Vn.c1 & Min. endcap enclosure of (Note `[v1_n2] <#v1_n2>`__) & &

.. _notes-11:

Notes
~~~~~

#. Vn.b1 is only required in one direction. The distance of the other
   direction must be at least Vn.b.

#. For at corners at least one side must be treated as an endcap and for
   the other sides rule Vn.c can be applied.

.. figure:: sg13/img/pdf/vian.pdf

   dimensions

.. _`s:tv1`:

TopVia1
-------

.. container:: tabular

   \|>

   p2.4cm\|>

   p10.5cm\|>p1.8cm\|

   | & &

   | TV1.a & Min. and max. width &
   | TV1.a & Min. and max. width & &

   | TV1.b & Min. space &
   | TV1.b & Min. space & &

   | TV1.c & Min. enclosure of &
   | TV1.c & Min. enclosure of & &

   | TV1.d & Min. enclosure of &
   | TV1.d & Min. enclosure of & &

.. figure:: common/img/pdf/topvia1.pdf

   dimensions

.. _`s:tm1`:

TopMetal1
---------

.. container:: tabular

   \|>

   p2.4cm\|>

   p10.5cm\|>p1.8cm\|

   | & &

   | TM1.a & Min. width &
   | TM1.a & Min. width & &

   | TM1.b & Min. space or notch &
   | TM1.b & Min. space or notch & &

   | TM1.c & Min. global density [%] &
   | TM1.c & Min. global density [%] & &

   | TM1.d & Max. global density [%] &
   | TM1.d & Max. global density [%] & &

.. figure:: common/img/pdf/topmetal1.pdf

   dimensions

.. _`s:tm1fil`:

TopMetal1:filler
----------------

pattern are required in order to reduce layout sensitivity due to metal
etching and CMP process steps.

.. container:: tabular

   \|>

   p2.4cm\|>

   p10.5cm\|>p1.8cm\|

   | & &

   | TM1Fil.a & Min. width &
   | TM1Fil.a & Min. width & &

   | TM1Fil.a1 & Max. width &
   | TM1Fil.a1 & Max. width & &

   | TM1Fil.b & Min. space &
   | TM1Fil.b & Min. space & &

   | TM1Fil.c & Min. space to &
   | TM1Fil.c & Min. space to & &

   | TM1Fil.d & Min. space to &
   | TM1Fil.d & Min. space to & &

.. figure:: common/img/pdf/topmetal1_filler.pdf

   dimensions

.. _`s:tv2`:

TopVia2
-------

.. container:: tabular

   \|>

   p2.4cm\|>

   p10.5cm\|>p1.8cm\|

   | & &

   | TV2.a & Min. and max. width &
   | TV2.a & Min. and max. width & &

   | TV2.b & Min. space &
   | TV2.b & Min. space & &

   | TV2.c & Min. enclosure of &
   | TV2.c & Min. enclosure of & &

   | TV2.d & Min. enclosure of &
   | TV2.d & Min. enclosure of & &

.. figure:: common/img/pdf/topvia2.pdf

   dimensions

.. _`s:tm2`:

TopMetal2
---------

.. container:: tabular

   \|>

   p2.4cm\|>

   p10.5cm\|>p1.8cm\|

   | & &

   | TM2.a & Min. width &
   | TM2.a & Min. width & &

   | TM2.b & Min. space or notch &
   | TM2.b & Min. space or notch & &

   | TM2.bR & Min. space of lines if, at least one line is wider than
     5.0 µm and the parallel run is more than 50.0 µm (Note
     `[tm2_n1] <#tm2_n1>`__, `[tm2_n2] <#tm2_n2>`__) &
   | TM2.bR & Min. space of lines if, at least one line is wider than
     5.0 µm and the parallel run is more than 50.0 µm (Note
     `[tm2_n1] <#tm2_n1>`__, `[tm2_n2] <#tm2_n2>`__) & &

   | TM2.c & Min. global density [%] &
   | TM2.c & Min. global density [%] & &

   | TM2.d & Max. global density [%] &
   | TM2.d & Max. global density [%] & &

.. _notes-12:

Notes
~~~~~

#. Violations can cause potential issues with TAPEs during backgrinding.

#. Not checked within regions.

.. figure:: common/img/pdf/topmetal2.pdf

   dimensions

.. _`s:tm2fil`:

TopMetal2:filler
----------------

pattern are required in order to reduce layout sensitivity due to metal
etching and CMP process steps.

.. container:: tabular

   \|>

   p2.4cm\|>

   p10.5cm\|>p1.8cm\|

   | & &

   | TM2Fil.a & Min. width &
   | TM2Fil.a & Min. width & &

   | TM2Fil.a1 & Max. width &
   | TM2Fil.a1 & Max. width & &

   | TM2Fil.b & Min. space &
   | TM2Fil.b & Min. space & &

   | TM2Fil.c & Min. space to &
   | TM2Fil.c & Min. space to & &

   | TM2Fil.d & Min. space to &
   | TM2Fil.d & Min. space to & &

.. figure:: common/img/pdf/topmetal2_filler.pdf

   dimensions

.. _`s:pas`:

Passiv
------

.. container:: tabular

   \|>

   p2.4cm\|>

   p10.5cm\|>p1.8cm\|

   | & &

   | Pas.a & Min. width &
   | Pas.a & Min. width & &

   | Pas.b & Min. space or notch &
   | Pas.b & Min. space or notch & &

   | Pas.c & Min. enclosure of (Note `[pas_n1] <#pas_n1>`__) &
   | Pas.c & Min. enclosure of (Note `[pas_n1] <#pas_n1>`__) & &

.. _notes-13:

Notes
~~~~~

#. Not checked outside of sealring (edge-seal-passive)

.. figure:: common/img/pdf/passiv.pdf

   dimensions

.. _`c:device_rules`:

Device Layout Rules
===================

.. _`c:bipolar`:

Bipolar Design Rules
--------------------

Bipolar design rules are not disclosed due to IP reasons. Additional
layers will be added during the tape out procedure for mask generation.
Changing the given layouts may result in catastrophic device
malfunction. The IHP library provides a number of predefined devices
shown in the follow sections. Do not modify these layouts/abstracts.

**Strict design rule:** Do not flatten the HBT layout cells and do not
place any shapes, except metal for connections, in bipolar regions. Use
pins on given metals to connect base, emitter and collector with
corresponding metal shapes. Any modification in bipolar transistor
results in non-working device.

**Device recognition:** For device recognition layer in combination with
TEXT labels and layer combinations are used for device recognition.

Pre-defined Transistor Layouts
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

+------------+-----------------+-----------------+-----------------+
| **Device** | **Emitter       | **Parameter**   | **Comment**     |
|            | width**         |                 |                 |
+============+=================+=================+=================+
| npn13G2    | :math:`\mat     | :math:`\mat     | :math:          |
|            | hrm{W_E=0.07u}` | hrm{L_E=0.9u}`, | `\mathrm{L_E}`: |
|            |                 | :math:`\mathrm{ | emitter length, |
|            |                 | N_x=1\dots10}`, | :math:          |
|            |                 | :math:          | `\mathrm{A_E}`: |
|            |                 | `\mathrm{A_E=N_ | emitter         |
|            |                 | x\left(0.07u\cd | area,\ :math:   |
|            |                 | ot L_E\right)}` | `\mathrm{N_x}`: |
|            |                 |                 | number of       |
|            |                 |                 | emitters in a   |
|            |                 |                 | row             |
+------------+-----------------+-----------------+-----------------+
| npn13G2L   | :math:`\mat     | :math           | :math:          |
|            | hrm{W_E=0.07u}` | :`\mathrm{L_E=1 | `\mathrm{L_E}`: |
|            |                 | .0u\dots2.5u}`, | emitter length, |
|            |                 | :math:`\mathrm  | :math:          |
|            |                 | {N_x=1\dots4}`, | `\mathrm{A_E}`: |
|            |                 | :math:          | emitter         |
|            |                 | `\mathrm{A_E=N_ | area,\ :math:   |
|            |                 | x\left(0.07u\cd | `\mathrm{N_x}`: |
|            |                 | ot L_E\right)}` | number of       |
|            |                 |                 | emitters in a   |
|            |                 |                 | row             |
+------------+-----------------+-----------------+-----------------+
| npn13G2V   | :math:`\mat     | :math           | :math:          |
|            | hrm{W_E=0.12u}` | :`\mathrm{L_E=1 | `\mathrm{L_E}`: |
|            |                 | .0u\dots5.0u}`, | emitter length, |
|            |                 | :math:`\mathrm  | :math:          |
|            |                 | {N_x=1\dots8}`, | `\mathrm{A_E}`: |
|            |                 | :math:          | emitter         |
|            |                 | `\mathrm{A_E=N_ | area,\ :math:   |
|            |                 | x\left(0.12u\cd | `\mathrm{N_x}`: |
|            |                 | ot L_E\right)}` | number of       |
|            |                 |                 | emitters in a   |
|            |                 |                 | row             |
+------------+-----------------+-----------------+-----------------+

Schematic Cross-section
~~~~~~~~~~~~~~~~~~~~~~~

.. figure:: sg13/device/bipolar/img/cross_section_g2.png

   Schematic cross-section of the SiGe:C hetero bipolar transistor

Design Rules
~~~~~~~~~~~~

The is formed by and ring.

The following rules do not apply: nSDB.e

General Design Rules
^^^^^^^^^^^^^^^^^^^^

.. container:: tabular

   \|>

   p2.4cm\|>

   p10.5cm\|>p1.8cm\|

   | & &

   | npnG2.a & NPN Substrate-Tie = AND &
   | npnG2.a & NPN Substrate-Tie = AND & &

   | npnG2.b & must enclose &
   | npnG2.b & must enclose & &

   | npnG2.c & enclosure of inside &
   | npnG2.c & enclosure of inside & &

   | npnG2.d & Min. unrelated , , , , space to &
   | npnG2.d & Min. unrelated , , , , space to & &

   | npnG2.d1 & Min. unrelated space to &
   | npnG2.d1 & Min. unrelated space to & &

   | npnG2.d2 & Min. unrelated space to &
   | npnG2.d2 & Min. unrelated space to & &

   | npnG2.e & Min. unrelated space to &
   | npnG2.e & Min. unrelated space to & &

   | npnG2.f & are allowed to overlap each other &
   | npnG2.f & are allowed to overlap each other & &

Device Related Design Rules
^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. container:: tabular

   \|>

   p2.4cm\|>

   p10.5cm\|>p1.8cm\|

   | & &

   | npn13G2.a & Min. and max. emitter length &
   | npn13G2.a & Min. and max. emitter length & &

   | npn13G2.bR & Max. recommended total number of emitters per chip &
   | npn13G2.bR & Max. recommended total number of emitters per chip & &

   | npn13G2L.a & Min. emitter length &
   | npn13G2L.a & Min. emitter length & &

   | npn13G2L.b & Max. emitter length &
   | npn13G2L.b & Max. emitter length & &

   | npn13G2L.cR & Max. recommended total number of emitters per chip &
   | npn13G2L.cR & Max. recommended total number of emitters per chip &
     &

   | npn13G2V.a & Min. emitter length &
   | npn13G2V.a & Min. emitter length & &

   | npn13G2V.b & Max. emitter length &
   | npn13G2V.b & Max. emitter length & &

   | npn13G2V.cR & Max. recommended total number of emitters per chip &
   | npn13G2V.cR & Max. recommended total number of emitters per chip &
     &

 

.. figure:: sg13/img/pdf/hbt.pdf
   name: f:hbt_g2

   HBT dimensions.

.. _`s:rsil`:

Rsil
----

Rsil represents the salicided n+ doped resistor.

**Device recognition:** Rsil = +

.. container:: tabular

   \|>

   p2.4cm\|>

   p10.5cm\|>p1.8cm\|

   | & &

   | Rsil.a & Min. width &
   | Rsil.a & Min. width & &

   | Rsil.b & Min. space to &
   | Rsil.b & Min. space to & &

   | Rsil.c & Min. extension over &
   | Rsil.c & Min. extension over & &

   | Rsil.d & Min. space to &
   | Rsil.d & Min. space to & &

   | Rsil.e & Min. enclosure of &
   | Rsil.e & Min. enclosure of & &

   | Rsil.f & Min. length &
   | Rsil.f & Min. length & &

.. _notes-14:

Notes
~~~~~

#. represents the resistor definition layer and is required for back
   annotation.

.. figure:: sg13/img/pdf/rsil.pdf

   dimensions

.. _`s:rppd`:

Rppd
----

Rppd represents the unsalicided p+ doped resistor.

**Device recognition:** Rppd = + +

.. container:: tabular

   \|>

   p2.4cm\|>

   p10.5cm\|>p1.8cm\|

   | & &

   | Rppd.a & Min. width &
   | Rppd.a & Min. width & &

   | Rppd.b & Min. enclosure of &
   | Rppd.b & Min. enclosure of & &

   | Rppd.c & Min. and max. space to &
   | Rppd.c & Min. and max. space to & &

   | Rppd.d & Min. enclosure of &
   | Rppd.d & Min. enclosure of & &

   | Rppd.e & Min. length &
   | Rppd.e & Min. length & &

.. figure:: sg13/img/pdf/rppd.pdf

   dimensions

.. _`s:rhigh`:

Rhigh
-----

Rhigh represents an unsalicided partial compensated low n-doped
resistor.

**Device recognition:** Rhigh = + + +

.. container:: tabular

   \|>

   p2.4cm\|>

   p10.5cm\|>p1.8cm\|

   | & &

   | Rhi.a & Min. width &
   | Rhi.a & Min. width & &

   | Rhi.b & and are identical (Note `[rhigh_n1] <#rhigh_n1>`__) &
   | Rhi.b & and are identical (Note `[rhigh_n1] <#rhigh_n1>`__) & &

   | Rhi.c & Min. and enclosure of &
   | Rhi.c & Min. and enclosure of & &

   | Rhi.d & Min. and max. space to &
   | Rhi.d & Min. and max. space to & &

   | Rhi.e & Min. enclosure of &
   | Rhi.e & Min. enclosure of & &

   | Rhi.f & Min. length &
   | Rhi.f & Min. length & &

.. _notes-15:

Notes
~~~~~

#. is only permitted within resistors. Apart from that, is generated
   automatically (see section `4.2 <#s:special_layers>`__).

.. figure:: sg13/img/pdf/rhigh.pdf

   dimensions

.. _`s:nmosi`:

nmosi and nmosiHV
-----------------

**Device recognition:** nmosi is recognized as an nmos device. The
difference of nmosi and nmosiHV is given by . There are special device
construction rules for this substrate isolated nmos device. These rules
will only be tested inside a closed ring of AND .

.. container:: tabular

   \|>

   p2.4cm\|>

   p10.5cm\|>p1.8cm\|

   | & &

   | nmosi.b & Min. enclosure of (Note `[nmosi_n1] <#nmosi_n1>`__) &
   | nmosi.b & Min. enclosure of (Note `[nmosi_n1] <#nmosi_n1>`__) & &

   | nmosi.c & Min. space to &
   | nmosi.c & Min. space to & &

   | nmosi.d & Min. width forming an unbroken ring around any (Note
     `[nmosi_n2] <#nmosi_n2>`__) &
   | nmosi.d & Min. width forming an unbroken ring around any (Note
     `[nmosi_n2] <#nmosi_n2>`__) & &

   | nmosi.e1 & A separate Iso-PWell contact unabutted to a nmosi device
     is not allowed &
   | nmosi.e1 & A separate Iso-PWell contact unabutted to a nmosi device
     is not allowed & &

   | nmosi.e2 & nmosi unabutted to an Iso-PWell-Activ tie is not allowed
     &
   | nmosi.e2 & nmosi unabutted to an Iso-PWell-Activ tie is not allowed
     & &

   | nmosi.f & Min. width to separate ptap in nmosi &
   | nmosi.f & Min. width to separate ptap in nmosi & &

   | nmosi.g & Min. overlap of over &
   | nmosi.g & Min. overlap of over & &

.. _notes-16:

Notes
~~~~~

#. Iso-PWell-Activ = AND AND

#. NWell-nBuLay = AND

#. NWell which is used as a ring for isolated PWell and carries active
   p-mos devices has to be carefully layed out in order to prevent latch
   up.

#. Recommendation: 1 mimimum PWell contact per 50 µm². To calculate
   voltage drops in PWell consider an average sheet resistance of 3 kΩ.

#. Recommendation: Use ptapsb Pcell to ensure proper isolated PWell
   connection. An example can be found in Cadence PDK’s example library.

.. _`s:isolbox`:

isolbox
-------

The isolbox structure is used to generate PWell regions isolated from
the global substrate. This enables the realization of substrate isolated
nmos transistors or resistors. We recommend to use only pcell offered
via PDK by IHP. The pins "isosub" and "bn" are not part of the layout
pcell and have to be placed manually in order to give designer more
flexibility.

**Device recognition:** isolbox = TEXT “isolbox” within ( enclosed by )

.. figure:: sg13/img/pdf/isolbox.pdf
   name: f:isolbox

   a) Cross-section and b) top view of the isolbox device. (\* These
   layers are inherently derived from drawing layers.)

.. _`s:schottky`:

Schottky diode
--------------

**Device recognition:** schottky_nbl1 = enclosed by ( and and and not )

The following rules do not apply: NW.c1, NW.e1, PWB.f1, CntB.a, LU.d

.. container:: tabular

   \|>

   p2.4cm\|>

   p10.5cm\|>p1.8cm\|

   | & &

   | Sdiod.a & Min. and max. enclosure of &
   | Sdiod.a & Min. and max. enclosure of & &

   | Sdiod.b & Min. and max. enclosure of &
   | Sdiod.b & Min. and max. enclosure of & &

   | Sdiod.c & Min. and max. enclosure of &
   | Sdiod.c & Min. and max. enclosure of & &

   | Sdiod.d & Min. and max. width inside &
   | Sdiod.d & Min. and max. width inside & &

   | Sdiod.e & Min. and max. length inside &
   | Sdiod.e & Min. and max. length inside & &

.. figure:: sg13/img/pdf/schottky.pdf
   name: f:schottky

   dimensions.

ESD Protection Devices
----------------------

For ESD protection of the chip, special clamp devices are provided.
Please refer to the ESD documents for details about protection level.
Also note that it is recommended to have I/O MOS devices with channel
length of at least 0.36 µm.

nmoscl_2
~~~~~~~~

Clamp device for limiting supply voltage.

**Device recognition:** nmoscl_2 = TEXT “nmoscl_2” within

Following rules do not apply: nmosi.e, Gat.a3

nmoscl_4
~~~~~~~~

Clamp device for limiting supply voltage.

**Device recognition:** nmoscl_4 = TEXT “nmoscl_4” within

Following rules do not apply: nmosi.e, Gat.a3

scr1
~~~~

**Device recognition:** scr1 = TEXT “scr1” within

Following rules do not apply: nmosi.c, nmosi.g, LU.d, Gat.a

.. _`s:pad`:

Pad Dimensions
--------------

**Device recognition:** Pad = ( + + ) +

Pad rules are tested only within recognition layer. Pad rules are only
tested on metal structures which are on same net as . The following
design rules must be also applied to solder bump pads and Cu pillar
pads.

.. container:: tabular

   \|>

   p2.4cm\|>

   p10.5cm\|>p1.8cm\|

   | & &

   | Pad.aR & Min. recommended width &
   | Pad.aR & Min. recommended width & &

   | Pad.a1 & Max. width &
   | Pad.a1 & Max. width & &

   | Pad.bR & Min. recommended space &
   | Pad.bR & Min. recommended space & &

   | Pad.d & Min. space to &
   | Pad.d & Min. space to & &

   | Pad.dR & Min. recommended to space (Note `[pad_n1] <#pad_n1>`__) &
   | Pad.dR & Min. recommended to space (Note `[pad_n1] <#pad_n1>`__) &
     &

   | Pad.d1R & Min. recommended to (inside chip area) space &
   | Pad.d1R & Min. recommended to (inside chip area) space & &

   | Pad.eR & Min. recommended , , exit width &
   | Pad.eR & Min. recommended , , exit width & &

   | Pad.fR & Min. recommended , , exit length &
   | Pad.fR & Min. recommended , , exit length & &

   | Pad.gR & (within ) enclosure of &
   | Pad.gR & (within ) enclosure of & &

   | Pad.i & without not allowed &
   | Pad.i & without not allowed & &

   | Pad.jR & No devices under allowed (Note `[pad_n2] <#pad_n2>`__) &
   | Pad.jR & No devices under allowed (Note `[pad_n2] <#pad_n2>`__) & &

   | Pad.kR & under not allowed (Note `[pad_n3] <#pad_n3>`__) &
   | Pad.kR & under not allowed (Note `[pad_n3] <#pad_n3>`__) & &

.. _notes-17:

Notes
~~~~~

#. Distance of opening to strongly depends on bonding procedure. For
   flip chip bonding via solder bumps (see section
   `6.9.1 <#s:solder>`__) or copper pillars (see section
   `6.9.2 <#s:pillar>`__) or manual bonding a bigger distance may be
   required. We strongly recommend 25 μm distance for wedge-wedge wire
   bonding.

#. Components under pads can be damaged by mechanical stress.

#. may be damaged during packaging process, we recommend not to use them
   below .

.. figure:: common/img/pdf/pad.pdf
   name: f:pad

   Pad dimensions.

.. _`s:solder`:

Solder Bump Rules
~~~~~~~~~~~~~~~~~

These rules are valid within pads used for solder bumping and flip chip
assembling. These pad rules are valid for 60 μm passive opening and 80
μm bump ball size. Bump ball standard is PacTech SAC305 (SnAgCu).

We recommend to use Solder Bump option in Pcell provided in the PDK.

For different geometries refer to design rule manual of our partner
PacTech or the design rule manual of your specific bumping provider.

**Device recognition:** SBumpPad = +

.. container:: tabular

   \|>

   p2.4cm\|>

   p10.5cm\|>p1.8cm\|

   | & &

   | Padb.a & size &
   | Padb.a & size & &

   | Padb.b & Min. space &
   | Padb.b & Min. space & &

   | Padb.c & Min. (within ) enclosure of &
   | Padb.c & Min. (within ) enclosure of & &

   | Padb.d & Min. space to &
   | Padb.d & Min. space to & &

   | Padb.e & Min. pitch (Note `[solder_n1] <#solder_n1>`__) &
   | Padb.e & Min. pitch (Note `[solder_n1] <#solder_n1>`__) & &

   | Padb.f & Allowed passivation opening shape (Note
     `[solder_n1] <#solder_n1>`__) &
   | Padb.f & Allowed passivation opening shape (Note
     `[solder_n1] <#solder_n1>`__) & &

.. _notes-18:

Notes
^^^^^

#. Underlying may have a different shape. This rule is not checked
   during DRC.

.. figure:: common/img/pdf/pad_solder.pdf
   name: f:solder

   Pad dimensions for solder bumping process.

.. _`s:pillar`:

Copper Pillar Rules
~~~~~~~~~~~~~~~~~~~

These rules are valid within pads used for assembly with copper pillars.
The given pad rules are valid for a number of different geometries
offered by our partner PacTech given in table `6.1 <#pillar_table>`__.

**Important:** Please note that pad opening may have an impact on final
testing. If the passivation openings are too small, wafer-level testing
may be prevented because the pad metal cannot be sufficiently contacted.

We recommend to use Solder Bump option in Pcell provided in the PDK.

**Device recognition:** CuPillarPad = +

\* Thickness of optional SnAg cap after reflow at peak temp 260 degree C
would be higher than that of after plating/ before reflow in the factor
of 1.4 - 1.7, depending on the SnAg height as well.

.. figure:: common/img/pdf/pad_pillar_stack.pdf
   name: f:pillar_stack

   Copper pillar layer stack with and without optional SnAg cap.

For different geometries than listed in table `6.1 <#pillar_table>`__,
refer to the design rule manual of our partner PacTech or the design
rule manual of your specific bumping provider.

The following table defines design rules for PacTech’s copper pillar
option with minimum passivation opening, copper pillar height and copper
pillar pitch.

.. container::
   :name: pillar_table

   .. table:: Valid pad geometries and design rules for Cu pillars.

      ====================== === === === ==========
      **Passiv opening**     35  40  45  **Padc.a**
      ====================== === === === ==========
      **Opening spacing**                **Padc.b**
      **Opening enclosure**              **Padc.c**
      **CuPillarPad pitch**              **Padc.e**
      **Cu pillar height**   ± 7 ± 7 ± 7 
      **Cu pillar diameter** ± 3 ± 3 ± 3 
      **Cu height (A)**      ± 2 ± 2 ± 2 
      **SnAg height\* (B)**  ± 1 ± 1 ± 2 
      ====================== === === === ==========

.. _notes-19:

Notes
^^^^^

#. Passivation openings highlighted in green are suited for on-wafer
   measurements

#. Pads with passivation openings of 45 μm and 55 μm are suited for PCB
   applications. Minimum recommended pitch 250 μm; recommended standard
   pitch 500 μm.

.. container:: tabular

   \|>

   p2.4cm\|>

   p10.5cm\|>p1.8cm\|

   | & &

   | Padc.a & size &
   | Padc.a & size & &

   | Padc.b & Min. space &
   | Padc.b & Min. space & &

   | Padc.c & Min. (within ) enclosure of &
   | Padc.c & Min. (within ) enclosure of & &

   | Padc.d & Min. space to &
   | Padc.d & Min. space to & &

   | Padc.e & Min. pitch (Note `[pillar_n1] <#pillar_n1>`__) &
   | Padc.e & Min. pitch (Note `[pillar_n1] <#pillar_n1>`__) & &

   | Padc.f & Allowed passivation opening shape (Note
     `[pillar_n1] <#pillar_n1>`__) &
   | Padc.f & Allowed passivation opening shape (Note
     `[pillar_n1] <#pillar_n1>`__) & &

.. _notes-20:

Notes
^^^^^

#. Underlying may have a different shape. This rule is not checked
   during DRC.

.. figure:: common/img/pdf/pad_pillar.pdf
   name: f:pillar

   Pad dimensions for copper pillar process.

.. _`s:seal`:

Sealring
--------

A sealring is an uninterrupted ring of metal and via layers. The purpose
of the sealring is to reduce the effects of mechanical stress on the
circuit that occurs during dicing of various chips. The sealring must be
enclosed by an unbrokend ring of . Figure `6.8 <#fig:seal>`__ shows
distance between and the sealring boundary (30 μm) and the passivation
opening. Please be aware that corresponding standard metal and via rules
are not checked within regions.

**Device recognition:**

.. container:: tabular

   \|>

   p2.4cm\|>

   p10.5cm\|>p1.8cm\|

   | & &

   | Seal.a & Min. , , , , width &
   | Seal.a & Min. , , , , width & &

   | Seal.b & Min. space to , , , , &
   | Seal.b & Min. space to , , , , & &

   | Seal.c & ring width &
   | Seal.c & ring width & &

   | Seal.c1 & ring width &
   | Seal.c1 & ring width & &

   | Seal.c2 & ring width &
   | Seal.c2 & ring width & &

   | Seal.c3 & ring width &
   | Seal.c3 & ring width & &

   | Seal.d & Min. enclosure of , , , ring &
   | Seal.d & Min. enclosure of , , , ring & &

   | Seal.e & Min. ring width outside of sealring &
   | Seal.e & Min. ring width outside of sealring & &

   | Seal.f & Min. ring outside of sealring space to , , , &
   | Seal.f & Min. ring outside of sealring space to , , , & &

   | Seal.k & Min. 45-degree corner length (Note
     `[seal_n1] <#seal_n1>`__) &
   | Seal.k & Min. 45-degree corner length (Note
     `[seal_n1] <#seal_n1>`__) & &

   | Seal.l & No structures outside sealring boundary allowed &
   | Seal.l & No structures outside sealring boundary allowed & &

   | Seal.m & Only one sealring per chip allowed (Note
     `[seal_n1] <#seal_n1>`__) &
   | Seal.m & Only one sealring per chip allowed (Note
     `[seal_n1] <#seal_n1>`__) & &

.. _notes-21:

Notes
~~~~~

#. Not checked during DRC

 

.. figure:: sg13/img/pdf/edgeseal.pdf
   name: fig:seal

   EdgeSeal and Sealring dimensions.

.. _`s:mim`:

MIM
---

Metal-Insulator-Metal (MIM) capacitors are formed by a thin dielectric
layer and conductor placed between , and .

Within capacitor layer can be used instead of . Some EDA tools cannot
distinguish between interconnects and electrical components which are
formed by the same conductive layers. Within the MIM device, can be
replaced with to prevent false short circuit detection.

**Device recognition:** MIM capacitor = +

.. container:: tabular

   \|>

   p2.4cm\|>

   p10.5cm\|>p1.8cm\|

   | & &

   | MIM.a & Min. width &
   | MIM.a & Min. width & &

   | MIM.b & Min. space &
   | MIM.b & Min. space & &

   | MIM.c & Min. enclosure of &
   | MIM.c & Min. enclosure of & &

   | MIM.d & Min. enclosure of &
   | MIM.d & Min. enclosure of & &

   | MIM.e & Min. space to &
   | MIM.e & Min. space to & &

   | MIM.f & Min. area per MIM device (µm²) &
   | MIM.f & Min. area per MIM device (µm²) & &

   | MIM.g & Max. area per MIM device (µm²) &
   | MIM.g & Max. area per MIM device (µm²) & &

   | MIM.gR & Max. recommended total area per chip (µm²) &
   | MIM.gR & Max. recommended total area per chip (µm²) & &

   | MIM.h & must be over &
   | MIM.h & must be over & &

.. figure:: sg13/img/pdf/mim.pdf
   name: f:mim

   dimensions

.. _`s:ind`:

Inductors
---------

In order to verify a custom inductor in the LVS check, additional layers
must be added to the actual inductor layout (see Fig.
`6.10 <#f:inductor>`__). The inductor must be completely enclosed by the
layer. To define the connection points, rectangles in layer must be
placed on the inductor metal. The connection points must touch the edge
of the layer and contain a pre-defined text label in layer . These text
labels are "LA" and "LB" for inductors with two connections or "LA",
"LB" and "LC" for inductors with three connections.

Parasitic extraction of metal lines is excluded from inductors defined
by this procedure. Within this layer there is by default no filler
generation.

Following rules will not be checked within this layer: metal slit rules,
AFil.g2, MFil.h, TM2.bR

.. figure:: common/img/pdf/inductor.pdf
   name: f:inductor

   Custom inductor connection method.

.. _`c:special`:

Special Rules
=============

.. _`s:antenna`:

Antenna Rules
-------------

The antenna effect occurs when metal layers on a chip are etched during
the semiconductor manufacturing process. As the metal layers are etched,
the remaining metal traces collect charge during the etching process.
When these metal traces discharge, it can lead to damage or unwanted
changes in the properties of the connected devices.

The design rules related to unprotected devices are determined by using
gate leakage current (shift of 10 % for nominal devices) as failure
criterion.

Antenna Rules are not checked by default. Antenna rule checking must be
switched on separately.

.. container:: tabular

   \|>

   p2.4cm\|>

   p10.5cm\|>p1.8cm\|

   | & &

   | Ant.a & Max. ratio of over field oxide area to connected area &
   | Ant.a & Max. ratio of over field oxide area to connected area & &

   | Ant.b & Max. ratio of cumulative metal area (from to ) to connected
     area (without protection diode) &
   | Ant.b & Max. ratio of cumulative metal area (from to ) to connected
     area (without protection diode) & &

   | Ant.c & Max. ratio of area to connected area &
   | Ant.c & Max. ratio of area to connected area & &

   | Ant.d & Max. ratio of cumulative via area (from to ) to connected
     area (without protection diode) &
   | Ant.d & Max. ratio of cumulative via area (from to ) to connected
     area (without protection diode) & &

   | Ant.e & Max. ratio of cumulative metal area (from to ) to connected
     area (with protection diode) &
   | Ant.e & Max. ratio of cumulative metal area (from to ) to connected
     area (with protection diode) & &

   | Ant.f & Max. ratio of cumulative via area (from to ) to connected
     area (with protection diode) &
   | Ant.f & Max. ratio of cumulative via area (from to ) to connected
     area (with protection diode) & &

   | Ant.g & Size of protection diode (µm²) (Note
     `[antenna_n4] <#antenna_n4>`__) &
   | Ant.g & Size of protection diode (µm²) (Note
     `[antenna_n4] <#antenna_n4>`__) & &

.. _notes-22:

Notes
~~~~~

#. The rules apply for both types of oxide.

#. Vn_area = cumulative area Cont, Via1 to TopVia2

#. Via_area = cumulative area Via1 to TopVia2

#. PDarea (µm²) = 0.02 x (Vn_area / (GatPoly over Activ)_area)

.. figure:: sg13/img/pdf/antenna_area_ratio.pdf
   name: f:antenna_area_ratio

   Cumulated area ratio calculation example.

.. math:: \mathrm{AreaRatio\left(G1\right)=\frac{Area\{M1\left(i\right)\}+Area\{M2\left(i\right)\}}{Area\{G1\}}+\frac{Area\{M3\left(i\right)\}}{Area\{G1\}+Area\{G2\}+Area\{G3\}}}

.. math:: \mathrm{AreaRatio\left(G2\right)=\frac{Area\{M1\left(ii\right)\}}{Area\{G2\}}+\frac{Area\{M2\left(ii\right)\}}{Area\{G2\}+Area\{G3\}}+\frac{Area\{M3\left(i\right)\}}{Area\{G1\}+Area\{G2\}+Area\{G3\}}}

.. figure:: sg13/img/pdf/antenna_stacked_vias.pdf
   name: f:antenna_stacked_vias

   Usage of stacked vias to avoid antenna area ratio violations. Please
   note that this figure is only an example. The stacked via method can
   be applied up to .

Recommendations
~~~~~~~~~~~~~~~

-  To get DRC clean layouts it is recommended to connect the antenna
   node to the output of the driver at low metal level to reduce the
   antenna area or connect the antenna node to a diode.

-  To get DRC clean layouts it is recommended to use stacked vias to
   connect large metal or via areas as shown in Fig.
   `7.2 <#f:antenna_stacked_vias>`__.

-  To protect the gate of an isolated nMOS transistors it is recommended
   to place the antenna-protection diode in a separate (non isolated)
   p-body region.

-  For applications which are especially sensitive to
   :math:`\mathrm{V_t}` variation or mismatch (sense amplifers, certain
   analog circuits, etc.), each gate should be tied directly to an
   nSD/PWell or pSD/NWell diode in Metal1.

.. _`s:latchup`:

Latch-up Guidelines
-------------------

Latch-up is an undesirable phenomenon in integrated circuit (IC) design
that can lead to the inadvertent creation of a low-impedance path
between the power supply rails or any other regions forming a parasitic
thyristor. The effect is trigged by unwated injection of charges into
this structure. This can lead to destruction of circuit parts due to
overcurrent.

Latch-up rules are not checked by default. Latch-up rule checking must
be switched on separately.

Latch-up Protection on Output Buffers
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

#. Connect source of NMOS and PMOS devices to VSS and VDD, respectively.

#. Connect drain of NMOS and PMOS devices directly to the output pad.

#. Place guard rings (VSS, VDD ties) around any NMOS and PMOS devices,
   which are directly tied to a pad.

#. Double guard rings (N-Well isolator and P+ isolator) should be
   inserted between n-channel and p- channel output buffers.

#. Double guard rings (N-Well isolator and P+ isolator) should be
   inserted between output buffers and internal circuit area.

.. figure:: sg13/img/pdf/latchup_cross_section.pdf
   name: f:latchup_xsect

   I/O latch-up protection scheme.

.. _`s:latchup_rules`:

Additional Rules for Subtrate and NWell Ties
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. container:: tabular

   \|>

   p2.4cm\|>

   p10.5cm\|>p1.8cm\|

   | & &

   | LU.a & Max. space from any portion of inside to an tie &
   | LU.a & Max. space from any portion of inside to an tie & &

   | LU.b & Max. space from any portion of inside to an tie &
   | LU.b & Max. space from any portion of inside to an tie & &

   | LU.c & Max. extension of an abutted tie beyond &
   | LU.c & Max. extension of an abutted tie beyond & &

   | LU.c1 & Max. extension of an abutted substrate tie beyond &
   | LU.c1 & Max. extension of an abutted substrate tie beyond & &

   | LU.d & Max. extension of tie tie beyond &
   | LU.d & Max. extension of tie tie beyond & &

   | LU.d1 & Max. extension of an substrate tie beyond &
   | LU.d1 & Max. extension of an substrate tie beyond & &

 

.. figure:: sg13/img/pdf/latchup.pdf
   name: f:latchup

   Latch-up protection rules.

.. _`s:slits`:

Metal Slits
-----------

Large areas of metal are subject to mechanical stress during production.
This can cause metal detachment from the oxide. The use of metal slits
leads to reduction of mechanical stress.

| Metal stands for all metal layers (, and ).
| Metal = + +

.. container:: tabular

   \|>

   p2.4cm\|>

   p10.5cm\|>p1.8cm\|

   | & &

   | Slt.a & Min. width &
   | Slt.a & Min. width & &

   | Slt.b & Max. width &
   | Slt.b & Max. width & &

   | Slt.c & Max. width without requiring a slit &
   | Slt.c & Max. width without requiring a slit & &

   | Slt.e & No slits required on bond pads &
   | Slt.e & No slits required on bond pads & &

   | Slt.e1 & No slits required on &
   | Slt.e1 & No slits required on & &

   | Slt.f & Min. enclosure of &
   | Slt.f & Min. enclosure of & &

   | Slt.g & Min. and space to &
   | Slt.g & Min. and space to & &

   | Slt.h1 & Min. space to and &
   | Slt.h1 & Min. space to and & &

   | Slt.h2 & Min. space to and &
   | Slt.h2 & Min. space to and & &

   | Slt.h3 & Min. space to and &
   | Slt.h3 & Min. space to and & &

   | Slt.h4 & Min. space to &
   | Slt.h4 & Min. space to & &

   | Slt.i & Min. density for any plate bigger than 35 µm x 35 µm [%] &
   | Slt.i & Min. density for any plate bigger than 35 µm x 35 µm [%] &
     &

.. figure:: sg13/img/pdf/slits.pdf
   name: f:slits

   Metal slits dimensions.

.. _`s:pin`:

Pin Layer Rules
---------------

Circuit designers should use only drawing purpose 0 (data types) for
layouts. Only exception is pin purpose 2 for symbolic pins. Data type 2
(purpose pin) is used for symbolic connectivity information. Pin areas
must be fully covered by drawing. These rules are tested because pin
areas are not used for mask generation and a potential issue due to
false postive LVS matchs.

.. container:: tabular

   \|>

   p2.4cm\|>

   p10.5cm\|>p1.8cm\|

   | & &

   | Pin.a & Min. enclosure of &
   | Pin.a & Min. enclosure of & & 0.00

   | Pin.b & Min. enclosure of &
   | Pin.b & Min. enclosure of & & 0.00

   | Pin.e & Min. enclosure of &
   | Pin.e & Min. enclosure of & & 0.00

   | Pin.f & Min. enclosure of &
   | Pin.f & Min. enclosure of & & 0.00

   | Pin.g & Min. enclosure of &
   | Pin.g & Min. enclosure of & & 0.00

   | Pin.h & Min. enclosure of &
   | Pin.h & Min. enclosure of & & 0.00

.. _`c:digital`:

Rules of Digital Design
=======================

.. _`s:digibnd`:

DigiBnd Layer
-------------

Digital designs can be marked with the layer. This layer must be used
when using IHP’s standard digital libraries. must enclose the complete
layout of the digital components. Within the layer the following design
rules are changed compared to the analog flow.

.. _`s:nwell_d`:

NWell
~~~~~

Refer to section `5.1 <#s:nwell>`__ for NWell standard rule definitions.

.. container:: tabular

   \|>

   p2.4cm\|>

   p10.5cm\|>p1.8cm\|

   | & &

   | NW.c1 & Min. enclosure of inside &
   | NW.c1 & Min. enclosure of inside & &

   | NW.d1 & Min. space to external inside &
   | NW.d1 & Min. space to external inside & &

   | NW.e1 & Min. enclosure of NWell tie surrounded entirely by in
     inside &
   | NW.e1 & Min. enclosure of NWell tie surrounded entirely by in
     inside & &

   | NW.f1 & Min. space to substrate tie in inside &
   | NW.f1 & Min. space to substrate tie in inside & &

.. _`s:cont_d`:

Cont
~~~~

Refer to section `5.14 <#s:cnt>`__ for Cont standard rule definitions.

.. container:: tabular

   \|>

   p2.4cm\|>

   p10.5cm\|>p1.8cm\|

   | & &

   | Cnt.c & Min. enclosure of &
   | Cnt.c & Min. enclosure of & &

.. _`s:nmosi_d`:

nmosi and nmosiHV
~~~~~~~~~~~~~~~~~

Refer to section `6.5 <#s:nmosi>`__ for nmosi and nmosiHV standard rule
definitions.

.. container:: tabular

   \|>

   p2.4cm\|>

   p10.5cm\|>p1.8cm\|

   | & &

   | nmosi.e1 & A separate Iso-PWell contact unabutted to a nmosi device
     is not allowed &
   | nmosi.e1 & A separate Iso-PWell contact unabutted to a nmosi device
     is not allowed & &

   | nmosi.e2 & nmosi unabutted to an Iso-PWell-Activ tie is not allowed
     &
   | nmosi.e2 & nmosi unabutted to an Iso-PWell-Activ tie is not allowed
     & &

.. _`s:digisub`:

DigiSub Layer
-------------

The layer is used to define an area of a layout in which substrate
contacts are extracted as a short instead of a resistive component. It
is assumed that the substrate in which the components are located has
the same potential as the metal connections that are connected to the
substrate contact. There is no voltage drop within the substrate.

.. _`s:sram`:

SRAM Layer
----------

SRAM cells can be marked with the layer. must enclose the complete
layout of the SRAM components. Within the layer the following design
rules are changed compared to the analog flow.

.. _`s:nwell_s`:

NWell
~~~~~

Refer to section `5.1 <#s:nwell>`__ for NWell standard rule definitions.

.. container:: tabular

   \|>

   p2.4cm\|>

   p10.5cm\|>p1.8cm\|

   | & &

   | NW.c & Min. enclosure of (thin gate oxide) &
   | NW.c & Min. enclosure of (thin gate oxide) & &

   | NW.d & Min. space to external &
   | NW.d & Min. space to external & &

.. _`s:activ_s`:

Activ
~~~~~

Refer to section `5.5 <#s:activ>`__ for Activ standard rule definitions.

.. container:: tabular

   \|>

   p2.4cm\|>

   p10.5cm\|>p1.8cm\|

   | & &

   | Act.c & Min. drain/source extension &
   | Act.c & Min. drain/source extension & &

.. _`s:gatpoly_s`:

GatPoly
~~~~~~~

Refer to section `5.8 <#s:gatpoly>`__ for GatPoly standard rule
definitions.

.. container:: tabular

   \|>

   p2.4cm\|>

   p10.5cm\|>p1.8cm\|

   | & &

   | Gat.a & Min. width &
   | Gat.a & Min. width & &

   | Gat.b & Min. space or notch &
   | Gat.b & Min. space or notch & &

   | Gat.c & Min. extension over (end cap) &
   | Gat.c & Min. extension over (end cap) & &

   | Gat.d & Min. space to &
   | Gat.d & Min. space to & &

.. _`s:psd_s`:

pSD
~~~

Refer to section `5.10 <#s:psd>`__ for pSD standard rule definitions.

.. container:: tabular

   \|>

   p2.4cm\|>

   p10.5cm\|>p1.8cm\|

   | & &

   | pSD.e & Min. overlap of when forming abutted substrate tie &
   | pSD.e & Min. overlap of when forming abutted substrate tie & &

   | pSD.g & Min. or width when forming abutted tie &
   | pSD.g & Min. or width when forming abutted tie & &

   | pSD.g & Min. enclosure of PFET gate (thin gate oxide) &
   | pSD.g & Min. enclosure of PFET gate (thin gate oxide) & &

   | pSD.g & Min. space to NFET gate (thin gate oxide) &
   | pSD.g & Min. space to NFET gate (thin gate oxide) & &

.. _`s:cont_s`:

Cont
~~~~

Refer to section `5.14 <#s:cnt>`__ for Cont standard rule definitions.

.. container:: tabular

   \|>

   p2.4cm\|>

   p10.5cm\|>p1.8cm\|

   | & &

   | Cnt.c & Min. enclosure of &
   | Cnt.c & Min. enclosure of & &

   | Cnt.d & Min. enclosure of &
   | Cnt.d & Min. enclosure of & &

   | Cnt.f & Min. on space to &
   | Cnt.f & Min. on space to & &

   | Cnt.g2 & Min. overlap of on &
   | Cnt.g2 & Min. overlap of on & &

.. _`s:m1_s`:

Metal1
~~~~~~

Refer to section `5.16 <#s:m1>`__ for Metal1 standard rule definitions.

.. container:: tabular

   \|>

   p2.4cm\|>

   p10.5cm\|>p1.8cm\|

   | & &

   | M1.b & Min. space or notch &
   | M1.b & Min. space or notch & &

   | M1.c1 & Min. endcap enclosure of &
   | M1.c1 & Min. endcap enclosure of & &

   | M1.i & Min. space of lines of which at least one is bent by
     45-degree &
   | M1.i & Min. space of lines of which at least one is bent by
     45-degree & &

.. _`s:mn_s`:

Metal(n=2-5)
------------

Refer to section `5.17 <#s:mn>`__ for Metal(n=2-5) standard rule
definitions.

.. container:: tabular

   \|>

   p2.4cm\|>

   p10.5cm\|>p1.8cm\|

   | & &

   | M1.b & Min. space or notch &
   | M1.b & Min. space or notch & &

   | M1.c1 & Min. endcap enclosure of &
   | M1.c1 & Min. endcap enclosure of & &

.. _`s:v1_s`:

Via1
----

Refer to section `5.19 <#s:v1>`__ for Via1 standard rule definitions.

.. container:: tabular

   \|>

   p2.4cm\|>

   p10.5cm\|>p1.8cm\|

   | & &

   | V1.c1 & Min. endcap enclosure of &
   | V1.c1 & Min. endcap enclosure of & &

.. _`s:vn_s`:

Via(n=2-4)
----------

Refer to section `5.20 <#s:vn>`__ for Via(n=2-4) standard rule
definitions.

.. container:: tabular

   \|>

   p2.4cm\|>

   p10.5cm\|>p1.8cm\|

   | & &

   | Vn.c1 & Min. endcap enclosure of &
   | Vn.c1 & Min. endcap enclosure of & &

.. _`c:lbe`:

Localized Backside Etching (LBE)
================================

The backside etching module is not qualified and not yet tested under
all conditions. The module is not available for SG13RH.

.. figure:: common/img/pdf/lbe_stack.pdf
   name: f:lbe_xsection

   cross-section.

.. container:: tabular

   \|>

   p2.4cm\|>

   p10.5cm\|>p1.8cm\|

   | & &

   | LBE.a & Min. width &
   | LBE.a & Min. width & &

   | LBE.b & Max. width &
   | LBE.b & Max. width & &

   | LBE.b1 & Max. area (µm²) &
   | LBE.b1 & Max. area (µm²) & &

   | LBE.b2 & Min. area (µm²) &
   | LBE.b2 & Min. area (µm²) & &

   | LBE.c & Min. space or notch &
   | LBE.c & Min. space or notch & &

   | LBE.d & Min. space to inner edge of &
   | LBE.d & Min. space to inner edge of & &

   | LBE.e & Min. space to and &
   | LBE.e & Min. space to and & &

   | LBE.f & Min. space to &
   | LBE.f & Min. space to & &

   | LBE.h & No ring allowed &
   | LBE.h & No ring allowed & &

   | LBE.i & Max. global density [%] &
   | LBE.i & Max. global density [%] & &

.. figure:: common/img/pdf/lbe.pdf
   name: f:lbe

   dimensions.

.. _`c:tsv`:

Through-Silicon Via for Grounding (TSV_G)
=========================================

The TSV_G module is not qualified and not yet tested under all
conditions. Please note that wafers processed at IHP have full backside
metallization.

.. figure:: common/img/pdf/tsv_cross_section.pdf
   name: f:tsv_xsect

   TSV module cross-section.

Areas with etched TSV ring are recognized by the layer. No grid check is
performed on layer .

.. container:: tabular

   \|>

   p2.4cm\|>

   p10.5cm\|>p1.8cm\|

   | & &

   | TSV_G.a & has to be a ring structure &
   | TSV_G.a & has to be a ring structure & &

   | TSV_G.b & Min. and max. width &
   | TSV_G.b & Min. and max. width & &

   | TSV_G.c & ring diameter &
   | TSV_G.c & ring diameter & &

   | TSV_G.d & Min. space &
   | TSV_G.d & Min. space & &

   | TSV_G.e & Min. space to , , , and &
   | TSV_G.e & Min. space to , , , and & &

   | TSV_G.f & Min. enclosure of &
   | TSV_G.f & Min. enclosure of & &

   | TSV_G.g & Min. enclosure of ring structure &
   | TSV_G.g & Min. enclosure of ring structure & &

   | TSV_G.i & Max. global density [%] &
   | TSV_G.i & Max. global density [%] & &

   | TSV_G.j & Max. coverage ratio for any 500.0 x 500.0 µm² chip area
     [%] &
   | TSV_G.j & Max. coverage ratio for any 500.0 x 500.0 µm² chip area
     [%] & &

 

.. figure:: common/img/pdf/tsv.pdf
   name: f:tsv

   TSV dimensions.

Change history
==============

+----------+--------+------------------------------------------------+
| Rev. 0.1 | -04-20 | Initial revision                               |
+----------+--------+------------------------------------------------+
| Rev. 0.2 | -03-08 | Document structure completely revised Add      |
|          |        | missing figures to rule sections Chapter       |
|          |        | `2 <#c:layertable>`__: Add layer isoNWell to   |
|          |        | 257:0 Chapter `3 <#c:general>`__: Add chapter  |
|          |        | "General Requirements" Chapter                 |
|          |        | `3.2 <#s:forbidden-layers>`__: Add NoDRC       |
|          |        | Chapter `4 <#c:terminology>`__: Add chapter    |
|          |        | "Terminology" Chapter                          |
|          |        | `4.2 <#s:special_layers>`__: Add introduction  |
|          |        | text, add PWell, nBuLay and Gate descriptions  |
|          |        | Chapter `5.1 <#s:nwell>`__: Update NW.c,       |
|          |        | NW.c1, NW.d, NW.d1, NW.e, NW.e1, NW.f, NW.f1   |
|          |        | rule descriptions, remove (old) note 3, update |
|          |        | (old) note 4 Chapter `5.2 <#s:pwellblock>`__:  |
|          |        | Update PWB.e, PWB.e1, PWB.f, PWB.f1 rule       |
|          |        | descriptions Chapter `5.3 <#s:nbulay>`__:      |
|          |        | Update introduction text, update note 1,       |
|          |        | remove note 2 Chapter `5.4 <#s:nblb>`__:       |
|          |        | Remove note 1, move note 2 into introduction   |
|          |        | text Chapter `5.6 <#s:actfiller>`__: Remove    |
|          |        | note 2, change AFil.b to 0.42 Chapter          |
|          |        | `5.8 <#s:gatpoly>`__: Move GatPoly:filler part |
|          |        | of Gat.c to (new) GFil.j, update Gat.g         |
|          |        | description Chapter `5.9 <#s:gatfiller>`__:    |
|          |        | Remove (old) Gat.j, move GatPoly:filler part   |
|          |        | of Gat.c to (new) GFil.j, remove note 2        |
|          |        | Chapter `5.10 <#s:psd>`__: Add introduction    |
|          |        | text Chapter `5.14 <#s:cnt>`__: Add            |
|          |        | introduction text Chapter `5.15 <#s:cntb>`__:  |
|          |        | Update introduction text Chapter               |
|          |        | `5.18 <#s:mfil>`__: Remove note 3, update note |
|          |        | 2 text, change MFil.b to 0.42 Chapter          |
|          |        | `5.23 <#s:tm1fil>`__: Add introduction text,   |
|          |        | remove note 1 Chapter `5.26 <#s:tm2fil>`__:    |
|          |        | Add introduction text, remove note 1 Chapter   |
|          |        | `6.4 <#s:rhigh>`__: Update note 1 Chapter      |
|          |        | `6.6 <#s:isolbox>`__: Update introduction      |
|          |        | text, remove table containing pcell parameters |
|          |        | Chapter `6.9 <#s:pad>`__: Update introduction  |
|          |        | text, update note 1 Chapter                    |
|          |        | `6.9.1 <#s:solder>`__: Merge note 1 und note   |
|          |        | 3, move note 1 to introduction text Chapter    |
|          |        | `6.9.2 <#s:pillar>`__: Merge note 1 und note   |
|          |        | 3, move note 1 to introduction text Chapter    |
|          |        | `6.10 <#s:seal>`__: Section renamed to         |
|          |        | "Sealring", update introduction text, remove   |
|          |        | note 2 and note 4, move note 1 to introduction |
|          |        | text, add Seal.m, update Seal.e and Seal.f     |
|          |        | descriptions Chapter `6.11 <#s:mim>`__: Remove |
|          |        | MIM.i, remove "Yield Enhancement Guideline"    |
|          |        | Chapter `6.12 <#s:ind>`__: Rename section to   |
|          |        | "Inductors", add explanation of the connection |
|          |        | method, add Fig. `6.10 <#f:inductor>`__, fix   |
|          |        | waived design rules Chapter                    |
|          |        | `7 <#c:special>`__: Remove section "Layer      |
|          |        | generation" (overview of generated layers can  |
|          |        | be found in section                            |
|          |        | `4.2 <#s:special_layers>`__), remove section   |
|          |        | "NoDRC", move sections "Grid Rules" and        |
|          |        | "Forbidden Layers" to chapter                  |
|          |        | `3 <#c:general>`__ Chapter                     |
|          |        | `7.1 <#s:antenna>`__: Move note 1 to           |
|          |        | introduction text Chapter                      |
|          |        | `7.2 <#s:latchup>`__: Add introduction text,   |
|          |        | change LU.c1 description to "Max. extention of |
|          |        | an abutted substrate tie beyond Cont" Chapter  |
|          |        | `7.3 <#s:slits>`__: Update introduction text   |
+----------+--------+------------------------------------------------+
|          |        | Chapter `8.1 <#s:digibnd>`__: Update           |
|          |        | introduction text Chapter                      |
|          |        | `8.1.1 <#s:nwell_d>`__: Change to subsection   |
|          |        | of section `8.1 <#s:digibnd>`__, align         |
|          |        | description to original descriptions in        |
|          |        | section `5.1 <#s:nwell>`__ Chapter             |
|          |        | `8.1.2 <#s:cont_d>`__: Change to subsection of |
|          |        | section `8.1 <#s:digibnd>`__ Chapter           |
|          |        | `8.1.3 <#s:nmosi_d>`__: Change to subsection   |
|          |        | of section `8.1 <#s:digibnd>`__ Chapter        |
|          |        | `8.2 <#s:digisub>`__: Update introduction text |
|          |        | Chapter `8.3 <#s:sram>`__: Update introduction |
|          |        | text Chapter `10 <#c:tsv>`__: Remove TSV_G.h,  |
|          |        | update TSV_G.g description, update Fig.        |
|          |        | `10.1 <#f:tsv_xsect>`__                        |
+----------+--------+------------------------------------------------+

Known issues
============

.. [1]
   as a drawing layer only valid if and are identical. E.g. rhigh
   resistor (see `6.4 <#s:rhigh>`__)
