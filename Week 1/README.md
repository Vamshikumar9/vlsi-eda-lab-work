8-Bit Ripple Carry Adder (RCA)

<img width="862" height="413" alt="rca" src="https://github.com/user-attachments/assets/67e9caef-ef8c-409d-b320-1117485189eb" />

The design adds two 8-bit binary numbers (num1 and num2) and produces a 9-bit result, including the final carry.
The first Full Adder adds the least significant bits.
Its carry output is passed to the next Full Adder.
This process continues up to the most significant bit.
The final carry becomes sum[8]



Simulation Results – 8-bit Ripple Carry Adder

<img width="985" height="617" alt="rca_ver" src="https://github.com/user-attachments/assets/8f48432a-e05a-44bb-afaf-c214b58339a0" />
The waveform confirms that the Ripple Carry Adder produces the correct sum for the applied inputs.
Signal	Value
num1	32
num2	23
sum_out	55
Verification: 32 + 23 = 55 ✓



4:1 Multiplexer Using Generate/For Loop – Verilog HDL

<img width="843" height="307" alt="mux_gen" src="https://github.com/user-attachments/assets/4139468e-fc39-4ec5-80f5-dbde556174c6" />
This implements a 4:1 Multiplexer  using Verilog HDL and a for loop inside an always block.
A 4:1 MUX has four input signals, two select lines, and one output. The select lines determine which input is transferred to the output.


4:1 Multiplexer (MUX) — Simulation & GTKWave Verification

<img width="988" height="622" alt="mux_gen_ver" src="https://github.com/user-attachments/assets/4ce41c48-69aa-4465-b904-be774dcd1fc3" />

The GTKWave waveform confirms that the output y correctly follows the selected input based on the sel[1:0] control signals.


4:1 Multiplexer — incomp_case Simulation & GTKWave Verification
<img width="987" height="625" alt="incomp" src="https://github.com/user-attachments/assets/fb00e4aa-c7e7-4981-b5e0-468bb647bdfd" />

The simulation confirms that the output y changes according to the selected input, validating the functionality of the 4:1 MUX RTL design.


4:1 Multiplexer — Yosys Synthesis & Gate-Level Netlist
<img width="1915" height="353" alt="incomp_syn" src="https://github.com/user-attachments/assets/0e7014d2-2a3f-4b30-842b-2fd4da5c760b" />

The synthesized design shows the internal implementation of the MUX using standard cells such as NAND, buffer, MUX, and D-latch cells. The diagram provides a clear view of how the RTL description is mapped into technology-specific logic cells.
This step demonstrates the RTL → Logic Synthesis → Gate-Level Netlist


2:1 Multiplexer — Ternary Operator Implementation & GTKWave Verification
<img width="988" height="626" alt="tmux" src="https://github.com/user-attachments/assets/a8db9ae2-e3b4-4b75-b9a3-97125d03f969" />

Implemented a 2:1 Multiplexer (MUX) using the Verilog ternary operator and verified its functionality through simulation in GTKWave.
This demonstrates a simple and efficient RTL implementation of a 2:1 MUX and its functional verification using simulation waveforms.

2:1 Multiplexer — Ternary Operator Synthesis Using Yosys
<img width="602" height="242" alt="tmux1" src="https://github.com/user-attachments/assets/3eab1f8b-445e-4e1d-b196-f45b8de48e86" />

The synthesis result shows that the ternary operator is mapped directly to a SKY130 standard-cell multiplexer (sky130_fd_sc_hd__mux2_1).
This demonstrates the RTL → Synthesis → Technology Mapping flow and shows how a simple Verilog construct is converted into a technology-specific standard cell.


4:1 Multiplexer — if Statement Simulation & GTKWave Verification
<img width="982" height="623" alt="if2" src="https://github.com/user-attachments/assets/639ba29d-cafe-4d76-9f85-a69503928b58" />

The waveform shows the changing input signals and corresponding output y, demonstrating the functional behavior of the MUX during simulation.
This experiment helps understand how conditional RTL constructs are interpreted during simulation and how the resulting design behavior can be verified using waveform analysis.


4:1 Multiplexer — if Statement Simulation & GTKWave Verification
<img width="590" height="155" alt="if2_1" src="https://github.com/user-attachments/assets/029eb725-9193-49cf-917c-3bf9d3367280" />

Implemented and simulated a 4:1 Multiplexer (MUX) using Verilog if-based conditional logic and verified its functionality using GTKWave.
The waveform shows the changing input signals and corresponding output y, demonstrating the functional behavior of the MUX during simulation.
This experiment helps understand how conditional RTL constructs are interpreted during simulation and how the resulting design behavior can be verified using waveform analysis.


3:1 Multiplexer — if Statement Simulation & GTKWave Verification
<img width="992" height="616" alt="inc_if" src="https://github.com/user-attachments/assets/732f5ecc-841f-4d2f-999c-d14d5e4c2f74" />

The GTKWave simulation shows the input signals and corresponding output y, confirming the functional behavior of the multiplexer for different input conditions.
This experiment demonstrates RTL coding with conditional statements, functional simulation, and waveform-based verification as part of the digital/VLSI design flow.



Unintentional Latch Inferred from Incomplete if Statement (incomp_if)
<img width="602" height="290" alt="if" src="https://github.com/user-attachments/assets/5362557a-4df9-49d5-bac5-1d5a0e44ec1b" />

This schematic illustrates hardware synthesis results generated by Yosys for an incomplete if statement in HDL code (Verilog/SystemVerilog).
Because all conditional branches were not fully specified (missing an else clause), the synthesizer infers a transparent D-Latch ($_DLATCH_P_) to preserve the previous output state when the condition evaluates to false.


Incomplete Conditional Structures Causing Latch Inference in Verilog
<img width="693" height="380" alt="inc" src="https://github.com/user-attachments/assets/cc3f95a6-9e57-48fc-a3ff-84668b32bfb5" />

This file demonstrates common coding mistakes in Verilog combinational logic that lead to unintended latch inference during synthesis:
When an output variable is not assigned a value under every possible input condition in a combinational block, the synthesis tool infers a hardware latch to store its previous value.


Verilog Multiplexer Implementations
<img width="666" height="790" alt="tbg" src="https://github.com/user-attachments/assets/618e8c61-cf07-49d3-a290-a34b62fce6af" />

This file compares three different approaches to implementing a 2-to-1 Multiplexer (MUX) in Verilog, highlighting sensitivity list errors that lead to simulation-synthesis mismatches:
Omitting data signals from an always block sensitivity list creates buggy behavioral simulations while synthesis tools may still infer pure combinational logic.



Unused Bit Optimization in Sequential Counter Circuit
<img width="470" height="277" alt="count_opt" src="https://github.com/user-attachments/assets/6d149383-86b3-4564-9492-507381ad2a1c" />

This Verilog module (counter_opt) demonstrates synthesis optimization when higher-order bits of an internal register are unused by output assignments:
Modern RTL synthesis tools perform automatic dead code and unused register elimination to minimize hardware footprint.



Synthesized Netlist Schematic for Counter Logic Optimization
<img width="597" height="93" alt="count_opt_1" src="https://github.com/user-attachments/assets/6500893f-48f2-473d-ac8e-1afb08624cdc" />

This gate-level netlist schematic illustrates the physical technology mapping result generated by Yosys target mapping to the SkyWater 130nm Standard Cell Library (sky130_fd_sc_hd) for the optimized counter_opt module
Visualizing synthesized netlists confirms that dead code and unreferenced state variables are successfully stripped down to minimal silicon footprint prior to place-and-route.


Constant Propagation and Sequential Optimization in Dual Flip-Flop Circuit
<img width="457" height="350" alt="const_5syn" src="https://github.com/user-attachments/assets/04ce1655-dd0d-4326-bd67-63092e2268f0" />

This Verilog module (dff_const5) demonstrates sequential logic synthesis optimization through constant propagation and pipeline propagation across multiple clock cycles
Assigning fixed literal values inside sequential blocks allows synthesis tools to replace complex logic driving flip-flop data inputs with direct tie-offs


GTKWave Simulation Results for Dual Flip-Flop Constant Assignment
<img width="997" height="633" alt="const5" src="https://github.com/user-attachments/assets/8147a8e7-d719-4116-97d3-cec970b9ac7e" />

This GTKWave waveform capture illustrates the functional simulation of the dff_const5 module, demonstrating the delayed state transition of output q relative to the reset deassertion



Synthesized Netlist Schematic for Dual Flip-Flop Circuit
<img width="587" height="98" alt="const_5" src="https://github.com/user-attachments/assets/3696d9bd-6d1e-46f0-a9f6-6897ff882301" />

This gate-level netlist schematic illustrates the technology mapping performed by Yosys targeting the SkyWater 130nm Standard Cell Library (sky130_fd_sc_hd) for the dff_const5 module



Constant Optimization and Complete Register Elimination in Dual Flip-Flop Circui
<img width="450" height="328" alt="const4_syn" src="https://github.com/user-attachments/assets/1807c7bd-f92b-43f8-b7b1-5a49ae908caf" />

This Verilog module (dff_const4) illustrates an edge case in sequential synthesis where constant initial values during reset match post-reset logic, enabling complete optimization of physical registers



GTKWave Simulation Results for Constant Output Circuit
<img width="998" height="526" alt="const_4l" src="https://github.com/user-attachments/assets/4e51d2fe-7d7b-4fb7-816e-8c423ecb8fa0" />

This GTKWave waveform capture demonstrates the behavioral simulation of the dff_const4 module, showing that the output signal remains static regardless of reset transitions or clock cycles



Synthesized Netlist Schematic Showing Complete Flip-Flop Optimization

<img width="392" height="378" alt="const_4" src="https://github.com/user-attachments/assets/9d9b9436-d9c1-40db-8077-06f7f150cfc0" />

This Yosys RTL synthesized schematic illustrates the ultimate result of constant optimization on the dff_const4 module, showing how redundant sequential elements are removed prior to technology mapping



Combinational Logic Optimization in Conditional Ternary Expression
<img width="397" height="115" alt="opt_check_2_src" src="https://github.com/user-attachments/assets/488fd946-f167-46e1-8e0c-043a9b3690b1" />

This Verilog module (opt_check2) illustrates how synthesis tools simplify conditional ternary expressions into fundamental logic gate primitives


Synthesized Netlist Schematic for Optimized Ternary Logic
<img width="522" height="172" alt="opt_check_2" src="https://github.com/user-attachments/assets/3cca0583-7f2a-426f-98ec-1e54d09dede7" />

Visualizing the gate-level schematic confirms that algebraic optimization reduces the logical construct to its minimal physical cell representation before place-and-route.



Synthesized Netlist Schematic for Optimized Ternary AND Logic
<img width="935" height="752" alt="cipb" src="https://github.com/user-attachments/assets/847cdaea-cd4a-42ba-8a9b-18c25ce3e1b8" />

This gate-level netlist schematic illustrates the physical technology mapping result generated by Yosys for the opt_check2 module


Combinational Logic Optimization in Conditional Ternary Expression
<img width="458" height="107" alt="opt_check_src" src="https://github.com/user-attachments/assets/906b1995-ecda-45f3-9dad-e10896f4794f" />

Conditional ternary operators with a constant zero output simplify to standard AND logic rather than multiplexer primitives
This gate-level netlist schematic illustrates the physical technology mapping result generated by Yosys for the opt_check module




Synthesized Netlist Schematic for Optimized Ternary AND Logic
<img width="592" height="172" alt="opt_check" src="https://github.com/user-attachments/assets/7f25900d-7d41-44ee-8f32-e562f0430689" />

Visualizing the gate-level schematic confirms that Yosys eliminates multiplexer overhead by simplifying ternary expressions with zero-value false branches into single 2-input AND gates.




Nested Ternary Logic Optimization to 3-Input AND Gate

<img width="477" height="132" alt="opt_check3src" src="https://github.com/user-attachments/assets/93f8e078-7e9b-48ea-a94c-936435441120" />

This Verilog module (opt_check3) demonstrates multi-level combinational optimization, showing how nested conditional ternary operators with constant zero fallbacks reduce to multi-input fundamental logic gates




Synthesized Netlist Schematic for Nested Ternary Logic
<img width="603" height="251" alt="opt_check3" src="https://github.com/user-attachments/assets/04b89ec6-25ea-45b6-b2e0-7642a721da80" />

Demonstrates Yosys's ability to collapse multi-level nested conditional logic into higher-order standard cells, improving performance by reducing total gate delays across combinational paths





Complex Multi-Level Ternary Expression Optimization

<img width="492" height="234" alt="opt_check4_src" src="https://github.com/user-attachments/assets/5a37c7e5-aa12-4c04-9a32-6cbdaa6a4c04" />

This Verilog module (opt_check4) demonstrates algebraic simplification of a complex nested ternary operator expression containing redundant conditional terms




Synthesized Netlist Schematic for Optimized Nested Logic

<img width="597" height="237" alt="opt_check4" src="https://github.com/user-attachments/assets/f125530e-c80a-4a8f-b59e-9a52a6d7336d" />

Visualizing the synthesized netlist confirms Yosys's ability to prune unused input signals (b) and collapse multi-level conditional ternary trees down to minimal 2-input equivalence primitives






Constant Assignment D-Flip-Flop with Asynchronous Reset

<img width="475" height="202" alt="const1" src="https://github.com/user-attachments/assets/b751a2fb-a119-485a-9727-03df4f0cc4c0" />

This Verilog module (dff_const1) demonstrates a simple sequential circuit where the register data input is tied to a constant high logic value




GTKWave Simulation Results for Single Flip-Flop Constant Assignment

<img width="997" height="392" alt="const1_syn" src="https://github.com/user-attachments/assets/1ea255ea-e033-4d02-96f1-5a5f806517bd" />

Confirms that q takes exactly 1 clock cycle to transition from 0 to 1 after reset goes low, demonstrating the need to retain a physical flip-flop cell post-synthesis.






Synthesized Netlist Schematic for Single Flip-Flop Circuit

<img width="592" height="121" alt="const1_logic" src="https://github.com/user-attachments/assets/b10f2808-d844-459d-937c-20cdbb96fc19" />

D-Flip-Flops with constant data inputs cannot be optimized away if their reset value differs from their operational data input value.
Synthesis eliminates intermediate combinational data logic by connecting the flip-flop's $D$-pin directly to the supply tie-off node (1'1)


