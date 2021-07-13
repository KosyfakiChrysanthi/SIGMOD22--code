# SIGMOD22 Paper: Provenance in Temporal Interaction Networks
#code 


Instructions for compiling and running the code

1) run make at your terminal to compile the code (compilation is done using gcc with -O3 flag)

2) To use the code, you will need a directed graph file in the following format:
numberofvertices
numberofinteractions
src1 dest1 time1 flow1...
src2 dest2 time2 flow2...
src3 dest3 time3 flow3...
...

An example graph file (graph.txt) is given in this distribution

3) Running ./provenance_tin <graph file> <k for topk origin provenance OR numgroups> <Window size (for sliding prov.)> <budget for BudgetProv> <reduction for BudgetProv>
- the following algorithms are run and their provenance information is shown at the output
	- No Provenance (baseline)
	- Least Recently Born
	- Most Recently Born
	- LIFO
	- FIFO
	- LIFO with path tracking
	- Proportional (Dense Vectors)
	- Proportional (Sparse Vectors)
	- Proportional (From Selected Vertices) 
	- Proportional (From Groups of Vertices)
	- Window-based Proportional 
	- Budget-based Proportional

Example of execution:
make
./provenance_tin graph.txt 2 3 3 2
