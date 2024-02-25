# Klass Semi-Dynamic Flipflop

## Basic Operation

* A block diagram of a semi-dynamic flip-flop (SDFF) is shown in Fig. 1. The circuit is composed of a dynamic front-end & a static backend, hence its designation. 
* The flop samples input D & produces output QB, which is the logic complement of D
* The circuit operates as follows: On the falling edge of clock CK, the flop enters the precharge phase. Node X is precharged high, cutting off node Q from the input stage. 
* The static latch INV5-6 holds the previous logic level of Q and QB. Since CKD is also low during precharge, node S remains high holding transistor N1 on. 
* The evaluation phase begins with the rising edge of clock CK. If input D is low (i.e., the flop is latching a zero) node X would remain high, held by the INV3-4 latch. 
Node Q would either remain low or will be discharged through transistors N4-5, driving QB high (See Fig. 2a). 
* Three gate delays after CK rises, node S will be driven low, turning transistor N1 off. This shut-off operation will 
prevent a subsequent low-to-high transition of D from discharging node X. This feature provides the flip-flop its edge-triggered nature.
* If input D were high prior to evaluation (i.e., the flop is latching a one), node X would be discharged through the pulldown path N1-3. The static latch INV3-4 
would hold the value of X even if input D were subsequently driven low. 
* The high-to-low transition of X will turn transistor P2 on, driving Q high and output QB low (See Fig. 2b). 
* The falling transition of X would also force node S to remain high, preventing the shut-off of transistor N1, which is unnecessary after node X has been discharged.

## Conditional Shutof

* Notice that by using a NAND gate coupled to node X and CKD, the shutoff of the pulldown path is conditioned to the state of input D. 
* If D is high prior to evaluation, signal CKD is blocked and no shutoff is performed.
* This feature allows reducing the sampling window by about one inverter delay, which means a shorter hold time for the flip-flop and a better input noise rejection.

# Weste Harris Working Process

* The Klass semidynamic flip-flop (SDFF) [Klass99] shown in Figure is a cross between a pulsed latch and a flip-flop. Like the Partovi pulsed latch, it operates on the
principle of intersecting pulses. 
* However, it uses a dynamic NAND gate in place of the static NAND. While the clock is low, X precharges high and Q holds its old state.
* When the clock rises, the dynamic NAND evaluates.
* If D is 0, X remains high and the top NMOS transistor turns OFF. If D is 1 and X starts to fall low, the transistor remains ON to finish the transition. This allows for a short pulse and hold time.
* The dynamic front end serves as the master latch, while the second stage serves as the slave. The weak cross-coupled inverters staticize the flip-flop and the final inverter buffers the output node.

* Like a pulsed latch, the SDFF accepts rising inputs slightly after the rising clock edge.
* Like a flip-flop, falling inputs must be set up before the rising clock edge. It is called semi-dynamic because it combines the dynamic input stage with static operation.
* The SDFF is slightly faster than the Partovi pulsed latch but loses the skew tolerance and time borrowing capability.
* It also has a higher energy consumption because of the large number of nodes with high activity factors.

## Detailed Working:

* On the falling edge of clock CK, the flip-flop enters the precharge phase. Node X is precharged high, cutting off node Q from the input stage.
* The static latch INV5-6 holds the previous logic level of Q and QB. Since CKD is also low during precharge, node S remains high, holding transistor N1 on. The evaluation phase begins with the rising edge of clock CK.
* If input D is low flip-flop is latching a zero-node X will remain high, held by the INV3-4 latch. Node Q either will remain low or will be discharged through transistors N4-5, driving QB high.
* Three gate delays after CK rises, node S is driven low, turning transistor N1 off. This shutoff operation prevents a subsequent low-to-high transition of D from discharging node X, thus providing the flip-flop its edge-triggered nature.
* If input D were high before evaluation flip-flop is latching a one-node X would be discharged through the pulldown path N1-3.
* The static latch INV3-4 would hold the value of X even if input D was subsequently driven low. The falling transition of X would turn transistor P2 on, driving Q high and output QB low.
* This would also force node S to stay high, preventing the shutoff of transistor N1, which is unnecessary after node X has been discharged.
* Notice that by using a NAND gate coupled to node X and CKD, the shutoff of the pulldown path is conditioned to the state of input D. If D were high before evaluation, signal CKD would be blocked and no shutoff would be performed.
* By strongly skewing inverters INV1-2 and the NAND gate, this modification allows the reduction of the sampling window by about one inverter delay at the expense of a small speed penalty for increased loading on node X.
* This feature yields a shorter hold time and better input noise rejection. Furthermore, the conditional shutoff makes the circuit less sensitive to variations of the sampling window that are due to manufacturing-process variations or unaccounted layout parasitics.

![1](https://github.com/SolankiPratikkumar/Layout-of-Klass-Semi-Dynamic-Flipflop/assets/140999250/b30a7524-5c76-4ba3-9822-cf42f0e2311c)
![2](https://github.com/SolankiPratikkumar/Layout-of-Klass-Semi-Dynamic-Flipflop/assets/140999250/93d17738-7c2b-42f9-a51f-afcc5f1c782b)

## Truth Table

![3](https://github.com/SolankiPratikkumar/Layout-of-Klass-Semi-Dynamic-Flipflop/assets/140999250/e8be75f0-2219-443b-8a50-7a69395a7c5c)

## Simulation Circuit on Cadence Virtuoso

![4](https://github.com/SolankiPratikkumar/Layout-of-Klass-Semi-Dynamic-Flipflop/assets/140999250/08b7a84a-2fef-40b3-b9b5-663d1cc7f562)

## Output and Nodes Waveform 

![5](https://github.com/SolankiPratikkumar/Layout-of-Klass-Semi-Dynamic-Flipflop/assets/140999250/d616079b-9804-499d-b1c3-acfaa5c2b6a0)
![6](https://github.com/SolankiPratikkumar/Layout-of-Klass-Semi-Dynamic-Flipflop/assets/140999250/4aaddcfa-6e9a-4dff-b63f-7262e307ae02)
![7](https://github.com/SolankiPratikkumar/Layout-of-Klass-Semi-Dynamic-Flipflop/assets/140999250/6fa1bee1-9549-4409-8431-3b8df131d373)
![8](https://github.com/SolankiPratikkumar/Layout-of-Klass-Semi-Dynamic-Flipflop/assets/140999250/1366b52b-3868-4265-9967-25a34da9f62f)
![9](https://github.com/SolankiPratikkumar/Layout-of-Klass-Semi-Dynamic-Flipflop/assets/140999250/bb223430-82bb-408a-b059-60f8d735a3f7)
![10](https://github.com/SolankiPratikkumar/Layout-of-Klass-Semi-Dynamic-Flipflop/assets/140999250/adc6ec7a-393b-426b-9050-1eb43f963a2c)

## Delay Values with Waveform

![11](https://github.com/SolankiPratikkumar/Layout-of-Klass-Semi-Dynamic-Flipflop/assets/140999250/5e847ec7-c51d-4ad8-9de1-e062f8c3956d)

RISE TIME: tpdr = 32.38ps
FALL TIME: tpdf = 9.38ps

## Setup Time

* Setup time is the required time duration that the input data MUST be stable before the triggering-edge of the clock.
* If data is changing within this setup time window, the input data might be lost and not stored in the flip-flop as metastability might occur.

**Parametric Analysis For Setup Time**

![12](https://github.com/SolankiPratikkumar/Layout-of-Klass-Semi-Dynamic-Flipflop/assets/140999250/921a18e6-8c28-4ca9-93c4-96e7bf5c0a98)

**Setup Time Waveform**

![13](https://github.com/SolankiPratikkumar/Layout-of-Klass-Semi-Dynamic-Flipflop/assets/140999250/605c5747-8cb1-4c14-aedf-7d0b9a6afd40)

* Minimum Setup Time from circuit Waveform = -12.57ps

## Hold Time

* Hold time is the required duration that the input data MUST be stable after the triggering edge of the clock.
* Similar to setup time violation, hold time violation will cause data metastability, and new data might not be correctly stored in the flip-flop

![14](https://github.com/SolankiPratikkumar/Layout-of-Klass-Semi-Dynamic-Flipflop/assets/140999250/1c1b0d64-4e6a-4234-8b1c-c9d329dbf63a)

**Hold Time Waveform**

![15](https://github.com/SolankiPratikkumar/Layout-of-Klass-Semi-Dynamic-Flipflop/assets/140999250/91466e18-fe3e-4e1a-9248-14ce79796d17)

* Minimum Setup Time from circuit Waveform = 19.84ps

# LAYOUT

![16](https://github.com/SolankiPratikkumar/Layout-of-Klass-Semi-Dynamic-Flipflop/assets/140999250/2da7318c-bd38-4ef3-81a3-aa094e6b7d7c)

# DRC(Design Rule Check) Report

![17](https://github.com/SolankiPratikkumar/Layout-of-Klass-Semi-Dynamic-Flipflop/assets/140999250/12a37292-c040-476f-92e0-497691e53e42)

![18](https://github.com/SolankiPratikkumar/Layout-of-Klass-Semi-Dynamic-Flipflop/assets/140999250/f193c73c-1552-43d4-81ba-f4f78419638b)

# LVS(Layout vs Schematics) Report

![19](https://github.com/SolankiPratikkumar/Layout-of-Klass-Semi-Dynamic-Flipflop/assets/140999250/628d8ab0-d2f0-4cfd-81de-c57bd5faa0db)

# Word of Thanks
I sincerely Thanks Prof.Madhav Rao for Teaching and Helping me to complete this project smoothly

# Acknowledgement

* Yogesh iMTech Colleague,IIITB
* Dilli Babu, MS by Research IIITB
* Vaibhav Tiwari, MTech, IIITB
  
# REFERENCE

* A New Family of Semidynamic and Dynamic Flip-Flops with Embedded Logic for High-Performance Processors Fabian Klass, Chaim Amir, Ashutosh Das, Kathirgamar Aingaran,
Cindy Truong, Richard Wang, Anup Mehta, Ray Heald, and Gin Yee
* CMOS VLSI Design: A Circuits and Systems Perspective by Weste/Harris (Author)
* Klass Fabian. 1998. “Semi-Dynamic and Dynamic flipflops with embedded Logic”. Sun Microsystems Inc. Palo Alto, CA 94303 USA
