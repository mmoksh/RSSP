# RSSP

## A Linear Delay Linear Space Algorithm for Enumeration of All Connected Induced Subgraphs

This  is the binary file for the implementation of the RSSP algorithm. The source code was written in C++, and compiled and tested on a Linux Ubuntu 14.04 machine.

## Installation
Change the permissions to make the binary file executable:

	chmod +x rssp

## Enumerating all connected induced subgraphs
	./rssp CIS GRAPH_INPUT_FILE [OUTPUT_FILE]

	- GRAPH_INPUT_FILE: specifies the location of a graph file in a simple space delimited adjacency list form.
	- OUTPUT_FILE: specifies the location of the output file. If skipped, the algorithm will enumerate all connected induced subgraphs (patterns) and outputs only the count of them.
	- If OUTPUT_FILE is `-`, then the patterns will be printed to the standard output.

### Example
	./rssp CIS input/toy_graph
	./rssp CIS input/toy_graph -
	./rssp CIS input/toy_graph output.txt

## Enumerating maximal cohesive subgraphs
	./rssp MCS GRAPH_INPUT_FILE ATTRIBUTES_INPUT_FILE MIN_SUP MIN_GRAPH_SIZE [OUTPUT_FILE]

	- GRAPH_INPUT_FILE: specifies the location of a graph file in a simple space delimited adjacency list form.
	- ATTRIBUTES_INPUT_FILE: specifies the location of the graph nodes' attributes file in a simple space delimited adjacency list form.
	- MIN_SUP: minimum number of similar properties
	- MIN_GRAPH_SIZE: minimum number of nodes in a maximal cohesive subgraphs
	- OUTPUT_FILE: specifies the location of the output file. If skipped, the algorithm will enumerate all connected induced subgraphs (patterns) and outputs only the count of them.
	- If OUTPUT_FILE is `-`, then the patterns will be printed to the standard output.

### Example
	Sample graph:
		./rssp MCS input/toy_graph input/toy_attributes 2 2
		./rssp MCS input/toy_graph input/toy_attributes 2 2 -
		./rssp MCS input/toy_graph input/toy_attributes 2 2 output.txt
	Human BIOGRID network:
		./rssp MCS input/HumanBIOGRID3.4.160.network.txt input/HumanBIOGRID3.4.160.Cancer.txt 8 3
		./rssp MCS input/HumanBIOGRID3.4.160.network.txt input/HumanBIOGRID3.4.160.Cancer.txt 8 3 -
		./rssp MCS input/HumanBIOGRID3.4.160.network.txt input/HumanBIOGRID3.4.160.Cancer.txt 8 3 output.txt

## Authors
* **Mohammed Alokshiya**
* **Saeed Salem**
* **Fidaa Abed**

## Last Updated August 9th, 2018
