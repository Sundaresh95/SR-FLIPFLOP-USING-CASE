# SR-FLIPFLOP-USING-CASE

**AIM:**

To implement  SR flipflop using verilog and validating their functionality using their functional tables

**SOFTWARE REQUIRED:**

Quartus prime

**THEORY**

SR Flip-Flop SR flip-flop operates with only positive clock transitions or negative clock transitions. Whereas, SR latch operates with enable signal. The circuit diagram of SR flip-flop is shown in the following figure.

<img width="641" height="413" alt="image" src="https://github.com/user-attachments/assets/98c59b09-cbde-4590-958f-c79a341387ad" />


 
This circuit has two inputs S & R and two outputs Qtt & Qtt’. The operation of SR flipflop is similar to SR Latch. But, this flip-flop affects the outputs only when positive transition of the clock signal is applied instead of active enable. The following table shows the state table of SR flip-flop.

<img width="613" height="321" alt="image" src="https://github.com/user-attachments/assets/f05646e2-15dc-4423-bcc4-493172a91594" />


 
Here, Qtt & Qt+1t+1 are present state & next state respectively. So, SR flip-flop can be used for one of these three functions such as Hold, Reset & Set based on the input conditions, when positive transition of clock signal is applied. The following table shows the characteristic table of SR flip-flop. Present Inputs Present State Next State

<img width="521" height="442" alt="image" src="https://github.com/user-attachments/assets/f9ef8992-51ed-4846-8b8d-7298acccb560" />


 
By using three variable K-Map, we can get the simplified expression for next state, Qt+1t+1. The three variable K-Map for next state, Qt+1t+1 is shown in the following figure.

<img width="600" height="212" alt="image" src="https://github.com/user-attachments/assets/b81ea6d3-5dda-46fc-83f6-c3e074b3df37" />


 
The maximum possible groupings of adjacent ones are already shown in the figure. Therefore, the simplified expression for next state Qt+1t+1 is Q(t+1)=S+R′Q(t)Q(t+1)=S+R′Q(t)

**Procedure**
Define Inputs/Outputs: Inputs: S (Set), R (Reset), c1k (clock); Outputs: Q, Qbar.
Initialization: Set Q = 0 and Qbar = 1 at the start of the simulation.
SR Flip-Flop Logic: On posedge c1k, compute Q = S | (~R & Q).
Complementary Output: Update Qbar = R | (~S & Qbar) to maintain SR Flip-Flop behavior.
Testbench: Test with combinations of S, R, and c1k to ensure proper Set-Reset functionality.


**PROGRAM**

module exp6(S,R,c1k,Q,Qbar);
input S,R,c1k;
output reg Q;
output reg Qbar;
initial Q=0;
initial Qbar=1;
always @(posedge c1k)
begin
Q=S|((~R)&Q);
Qbar=R|((~S)&(Qbar));
end
endmodule


**RTL LOGIC FOR FLIPFLOPS**
<img width="1109" height="666" alt="image" src="https://github.com/user-attachments/assets/f931525b-e8aa-4b71-9a83-0a939f8a2661" />

**TIMING DIGRAMS FOR FLIP FLOPS**
<img width="1921" height="1201" alt="image" src="https://github.com/user-attachments/assets/7773ab0f-4fe3-4984-8a45-aaf42b694942" />

**RESULTS**
Thus the SR flipflop is implemented and verified.
