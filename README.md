# AdvancedPhysicalDesign
## BE ORIGINAL AND FOLLOW CAD Communicate, Automate, and Document :Prof.Matthew Guthaus
<details>
<summary> Few more things about GitHub: </summary>
  
1.  A file named .gitignore can be used in the repository. This will alert GitHub to ignore particularr tasks, file,s and folders. https://www.freecodecamp.org/news/gitignore-what-is-it-and-how-to-add-to-repo/ 
2. Various licensess and a guide to use these are available in github. These can be intiated while creating the repository. Failing which default copyrights will be applied. https://docs.github.com/en/repositories/managing-your-repositorys-settings-and-features/customizing-your-repository/licensing-a-repository <br />
![image](https://user-images.githubusercontent.com/16399079/182571335-2513b1d8-2ff3-4f37-bc31-9053c7bfab06.png)
</details>

<details>
<summary> About MPW shuttle program: </summary>

 This is a program which helps fabricate chips by collaboration. Many open source projects are made availabale by efabless. More information is available at
https://platform.efabless.com/projects/shuttle_11
</details>

<details>
<summary> Creating github repo link: </summary>

One good reference https://github.com/ShonTaware 
</details>

# DAY -1 ADVANCED PHYSICAL DESIGN USING OPENLANE/SKY130
<details>
<summary> THEORY </summary>
  
## Understanding how to talk to computers
  1. ISA--> RTL --> LAYOUT
  2. Example: C Programme --> Assembly --> Machine -(*)-> Hardware layout
    (*) Happens by using RTL which follows RISCV
  3. Another way of putting it : C -compiler->Instr1,instr2.... -assembler-> binary--> layout
    The instructions are dependant on architecture such as x86/ARM/MIPS/RISCV
 ## New Terminologies learnt
  1. Board diagram : High level diagram showing what are on the PCB
  2. Package : The way a chip is package and connecting leads are providing for external world.
    Example ATMEL in Arduino UNO is QFN48 meaning Quad Flat No Leads with 48 pins
  3. Wire bonds : IC to package pins connection
  4. IPs and Macros : Macros are pure digital logic
  5. Foundry IPs: IPs provided by Foundry
  6. ISA : Instruction Set Architecture is language of computers (hardware)
  7. RISCV (p. Risk Five): is the industry standard on defining ISA architecture 
 ## Future Scope
  Yet to study detailed ASIC flow and Antenna Check and what is abc
  ![image](https://user-images.githubusercontent.com/16399079/182761756-41d3be14-4411-4e72-af64-54337d567d4c.png)
 
</details>

<details>
<summary> LAB </summary>
  
## System Configuration
  1. Working on online lab instance hosted at remotespark.com
  2. 
  ![image](https://user-images.githubusercontent.com/16399079/182762122-716a2f53-16a3-4833-b003-42a783dbac88.png)
  
  3. For installing on local PC lINUX version 18 is recommended
  4. All lab related works will be under 
  ```Desktop/work/tools/openlane_working_dir/openlane/```
  
## Day 1 progress
  1. Complete execution can be interactive or automated
  ![image](https://user-images.githubusercontent.com/16399079/182762612-038edb5b-ef72-4358-be9e-92b53b3fc601.png)
  2. prepare one design for running 
  ![image](https://user-images.githubusercontent.com/16399079/182762922-3592d927-522d-4682-93b1-0e801564a733.png)
  3. many designs are available at
  ![image](https://user-images.githubusercontent.com/16399079/182763061-ea3930a1-8a03-49b4-8da0-39964111b8a5.png)
  4. prep command prepares picorv32a design with following environment (folder named timestamp are obtained)
  
  ![image](https://user-images.githubusercontent.com/16399079/182763383-4746d69d-1585-4b55-aa83-3db61b3fc371.png)
  5. Run all commands in sequence
  6. Refer https://github.com/efabless/openlane for all details
    https://www.youtube.com/watch?v=EczW2IWdnOM
    https://www.youtube.com/watch?v=Vhyv0eq_mLU
  7. Somehow run commands are missing in github readme
    ![image](https://user-images.githubusercontent.com/16399079/182774987-70e316a7-7044-456f-be22-2e173707a5bb.png)
  8. run_synthesis, floorplan, placement and sta worked fine. problem with abc. waiting for solution

 
</details>

<details>
<summary> FAQ </summary>
  
 1. pandas not found error if docker command is not run
 2. to exit safely from a ```less``` command press q. Ctrl+B stops complete bash 

</details>

# DAY -2 Good floorplan vs bad floorplan and introduction to library cells
<details>
<summary> THEORY </summary>
  
## Floorplanning and considerations
  1. Wafers are madeup of Die. Die is madeup of cores.  
  ![image](https://user-images.githubusercontent.com/16399079/182810513-09f5173b-618d-4070-8ef4-8e3e6759e1e8.png)
  2. Utilization factor is area taken up by standard cells forming the core to the area of core.
  ![image](https://user-images.githubusercontent.com/16399079/182810386-67eb8244-85cb-4d3a-9351-03281e7b93de.png)
  3. Preplaced cells are the IPs which are placed at user defined locations. Remaining logical cells are placed by automated placement and routing.
  4. New way of defining noise margins.
  ![image](https://user-images.githubusercontent.com/16399079/182820609-8d75bf21-9834-499b-b415-0f8453727752.png)
  5. Decoupling capacitor decouples a ciruit receiving supply from the supply which is at a far place.
  ![image](https://user-images.githubusercontent.com/16399079/182832384-2c9862ab-eee5-4fd9-85f4-27f681730b1c.png)
  6. Power planning to avoid voltage droop and ground bounce
  ![image](https://user-images.githubusercontent.com/16399079/182865684-0923efdb-ed3d-467c-91a4-65a6f5788882.png)
  7. Solution
  ![image](https://user-images.githubusercontent.com/16399079/182866140-7f94e8f5-2c78-48e5-90ba-4d05fc25395c.png)
  ![image](https://user-images.githubusercontent.com/16399079/182866602-87b724bb-58e7-4d62-84f1-aeb94bee6a70.png)
  8. Netlist is the connectivity of gates described using HDLs.
  9. Block area for pins
  ![image](https://user-images.githubusercontent.com/16399079/182869503-d8c5de54-cbf5-4403-a589-cd131ec02350.png)

  ## Library Binding and Placement
  1.  Cells in netlist are square or rectangle shaped. combination and details of these cells forms a library. details like timing, area etc
  2. Library may have different flavours which help designers pickup based on size timing shapes etc.
  ![image](https://user-images.githubusercontent.com/16399079/183276842-e360a257-3707-49cb-b15c-c0b055aa89db.png)
  3. Placement is placing of netlist (cells) onto a floor which is planned with input output pins, io padded and grid of supplies and preplaced cells if available. (Study more)
  ![image](https://user-images.githubusercontent.com/16399079/183276863-cfc525d1-818d-4177-908e-d92e491c58bf.png)
  4. Repeaters are buffers which replicate the original signal and helps maintain signal integrity.
  5. Insert repeaters by estimaitng wire length and capacitance.
  6. Placing cells close to one another is abuttment which helps achieve very high speed.
  
  ## Library and timing charcterization
  1. Logic synthesis --> floorplan (size of die) --> placement (maintian timing) --> CTS (Clock should reach evrywhere on time) --> routing () --> STA (optional)
  ![image](https://user-images.githubusercontent.com/16399079/183277577-07482156-51e9-44d3-af57-0057c3001cc6.png)
  2. steps in characterization flow. GUNA software takes care of 1-8 steps.
  ![image](https://user-images.githubusercontent.com/16399079/183284448-23934ee1-3306-44b0-90e9-f47eb423bd3c.png)
  3. Timing characterization:
  Slew is between cells. rise and fall for all signals.
  ![image](https://user-images.githubusercontent.com/16399079/183284833-15c71b1c-42a1-4cae-910b-43dabb269808.png)
  4. Propagation delay.Choosing threold points is very importnat
    Negative delay is not permitted. wire delays are to be observed.
  ![image](https://user-images.githubusercontent.com/16399079/183284970-43709e42-e8d6-45c7-b60c-3e9c781a6684.png)
  
  ## Cell design flow
  1.
  ![image](https://user-images.githubusercontent.com/16399079/183278806-86333fe2-5ca6-43d4-b7af-5d01729e5169.png)
  2. Use PDKs, rules, spice and lib user defined specs to design
  3. Importance of analog design
  ![image](https://user-images.githubusercontent.com/16399079/183279330-d8f39fd4-a148-4db6-a9f6-407e395d9b70.png)
  4. Layout  
  ![image](https://user-images.githubusercontent.com/16399079/183279579-d07b8187-6dd7-4c92-b15b-b9ca16264fad.png)
  5. 
  ![image](https://user-images.githubusercontent.com/16399079/183279621-a0a2f8fe-44de-4d17-bc28-d783c553585f.png)

## Future Scope
  1. Placement vs Floorplanning
 
</details>

<details>
<summary> LAB </summary>
 
## Day 2 progress
  1. Learn variable from openlane/configuration folder / README.md and remaining tcl files show default config of openlane for FP/ROUTING etc
  ![image](https://user-images.githubusercontent.com/16399079/182871761-e3c163b3-7657-46c5-aa4b-19897a5890b2.png)
  2. metals used for picorv32a design visit config.tcl under picorv32a. But somehow i couldnt see that info. I got
  ![image](https://user-images.githubusercontent.com/16399079/182881423-58f5590b-64e7-41c7-a03a-3a93e4e214e1.png)
  3. Metals to be used are to be specified in config.tcl. Point 3 above is wrong
  4. tapcell is used for connecting nwell to vdd. decap around blocks and endcap at the pins.
  5. We can see results of floorplan as below. opening png file in online lab instance caused freeaing. so avoiding
  ![image](https://user-images.githubusercontent.com/16399079/183065821-c365352e-17db-4090-a5a3-26cdaf9039ab.png)
  6. Die area can be seen by visitin .def file in reults of floorplan
  ![image](https://user-images.githubusercontent.com/16399079/183066721-da252f4d-0009-4b7d-972e-92da244488e1.png)
  7. Unable to invoke magic from working terminal. But it can be launched directly from magic folder. 
  <img width="973" alt="image" src="https://user-images.githubusercontent.com/16399079/183234512-5e6ac7dd-6656-48d6-a958-0914e366f185.png">
  Shoul have got this
  <img width="594" alt="image" src="https://user-images.githubusercontent.com/16399079/183234523-3f38ab4e-1a1f-4470-a119-ea3df7fdf8c6.png">
  8. thanks to Nickson, magic command worked from shell. Earlier i was trying from openlane prompt.
  <img width="773" alt="image" src="https://user-images.githubusercontent.com/16399079/183235261-0b65df3f-ca18-421c-92c2-b2adea07fc52.png">
  9. S select V fit to window. left click bottom left- right click top right. click z for zooming
  10. Observe different parts of floorplan and standard cells at bottom left corner.
  ![image](https://user-images.githubusercontent.com/16399079/183276536-3f43b0fc-f03f-4d37-a74b-0b661875ef89.png)
  11. use overwte option to prep design earlier completd synthesisized design.
  12. Got results from placement folder using magic 
  ![image](https://user-images.githubusercontent.com/16399079/183278211-37dbde46-1277-4627-9787-782b8355d9b6.png)
  13. Observed mux, gates, m3, m4 , buffers vias etc taps decaps
  ![image](https://user-images.githubusercontent.com/16399079/183278439-fe84f175-aec5-4490-9184-0c4a1617d330.png)
  14
  
  

 </details>

<details>
<summary> FAQ </summary>
  
 1. 

</details>

# DAY -3 Design library cell using Magic Layout and ngspice characterization
<details>
<summary> THEORY </summary>
  
## VTC SPICE simulations
  1. Understanding spice deck
  ![image](https://user-images.githubusercontent.com/16399079/183286593-fbcc3c0c-0f80-4fdf-9c0e-288ec17be611.png)
  2. keeping pmos 1.5 to 2 times NMOS will provide symmetrical dc transfer characteristics.
  3. Switching threshold vm is the point where vin=vout.
  4. calculating delay , rise and fall times
## 16 mask process (Twin Tub)
  1. LOCOS, Bird's Peak, LOCOs helps isolate transistors.
  2. Ion plantation for forming wells for Pmos and nmos
  3. Put in furnace, wells which are implanted expand by diffusion.
  4. Gate formation is very important as it decides Vt. Vt is dependent on oxide Capacitance and doping concentration
  ![image](https://user-images.githubusercontent.com/16399079/183288080-c8ffe07b-49df-45f1-953f-4d03fa9e92a1.png)
  5. lambda=L/2
  6. Lightly doped drain LDD
  7. sIDE Wall spacers
  8. High Temp annealing
  9. metallization by sputtering
  10. Final
  ![image](https://user-images.githubusercontent.com/16399079/183288986-594e44b5-45a8-4945-ba28-5f68a3c5d75a.png)

## Future Scope
  1. 
  
</details>

<details>
<summary> LAB </summary>
 
## Day 3 progress
  1. lEARNING PLACMENET OF IO PINS from automatic equidistant to custom 
  set ::env(FP_IO_MODE) 2 IN FLOORPLAN.TCL
  ![image](https://user-images.githubusercontent.com/16399079/183285684-15a2955b-199f-492b-9435-e69ba72aef38.png)
  2. Unable to view any chnges happening. Same with earlier variations in all steps of flow. Complete tcl flow for all configs is to be studied
  3. learning git clone and copied tech file
  ![image](https://user-images.githubusercontent.com/16399079/183287304-7093d4f7-a486-4b74-a35f-befb5ea31570.png)
  4. Observing layout
  ![image](https://user-images.githubusercontent.com/16399079/183287372-22059863-d749-4819-a07e-1eefa96b799d.png)
  5. Check functionality of  inverter using ngspice. first extract .ext file
  <img width="650" alt="image" src="https://user-images.githubusercontent.com/16399079/183299910-460a0869-f9d8-43aa-bd9a-2963c44b8b9d.png">

  
 </details>

<details>
<summary> FAQ </summary>
  
 1. 

</details>
