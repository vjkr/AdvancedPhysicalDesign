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

# DAY -2 ADVANCED PHYSICAL DESIGN USING OPENLANE/SKY130
<details>
<summary> THEORY </summary>
  
## Good floorplan vs bad floorplan and introduction to library cells
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



 </details>

<details>
<summary> FAQ </summary>
  
 1. 

</details>
