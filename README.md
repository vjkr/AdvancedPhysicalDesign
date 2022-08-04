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
