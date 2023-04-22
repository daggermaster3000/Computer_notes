[[RISC vs CISC]]
Reduced Instruction Set Computer or Load/Store architecture
Representative: [[Alpha]]

### Pipeline processing
The instructions reside in memory that takes one cycle to read.
![[Pasted image 20221028144855.png]]
|Command|What it does| Full name|
|------------|--------------|-----------|
|IF|  |Instruction Fetch|
|ID||Instruction Decode|
|EX||Execute|
|MEM||Memory access|
|WB||Write back|
### Improvement of execution speed

#### Superpiplining
![[Pasted image 20221203114028.png]]

#### Superscalar Architecture
Multiple parralel piplines
![[Pasted image 20221203114018.png]]
### [[Hazards]]

## Evolution of Risc processors


- further increase of parallelization: 
	- more pipelines 
	- 4 instructions per cycle $\rightarrow$ superscalar 4 integer pipelines 
	- 2 floating point pipelines