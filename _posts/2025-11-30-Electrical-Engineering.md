---
layout: post
title: How Transistors and Logic Gates Power Computing
category: Electrical Engineering
---

So, we all know computers run on bits 1s and 0s. But what do those actually represent?

At the physical level, a **bit** is represented by the presence or absence of electrical voltage in a circuit. A **1** means there's a high voltage (typically around 3.3V or 5V), and a **0** means low or no voltage (close to 0V). This binary state is how computers encode and process all information.

Now, about electricity: it involves the flow of **electrons**, which are negatively charged particles. Electrons move from areas with excess electrons (negative charge) to areas with a deficit (positive charge). This movement is driven by **voltage**, which acts like electrical pressure pushing the electrons through a wire.

To clarify some analogies:
- **Voltage** = electrical "pressure"
- **Current (Amperes)** = amount of charge flowing past a point per second
- **Power (Watts)** = voltage × current (rate of energy use)
- **Resistance** = how much a material resists the flow of current (like the narrowness of a pipe)

Now, back to bits.

A **transistor** is a tiny electronic switch that controls whether current flows. Modern transistors are **MOSFETs** (Metal-Oxide-Semiconductor Field-Effect Transistors), and they have three parts:
- **Source** (input)
- **Drain** (output)
- **Gate** (control)

When a voltage is applied to the **gate**, it creates a conductive path between the source and drain, allowing current to flow—this is the **on (1)** state. No gate voltage means **off (0)**.

Transistors are used to build **logic gates**, which perform basic operations like AND, OR, and NOT. For example:
- An **AND gate** outputs 1 only if **both** inputs are 1.
- This is done by combining transistors (typically both nMOS and pMOS in CMOS technology) in specific configurations.

All complex operations in a processor addition, memory, decision-making are built from these simple logic gates. Millions or billions of transistors are packed into a single chip, forming circuits like adders, registers, and entire CPUs.

In short:  
**Electricity → Voltage states → Transistors as switches → Logic gates → Binary operations → Full computing power.**
