# LoRaSim-Extend Introduction

LoRa Simulator - Extended for evaluating LoRa network heterogeneous IoT applications,in this papaer I want to tackle different aspects of the technologies, the important one is capacity, i.e. the max generation rate of messages which can be send using the technology per second by devices.And several types of applications, generating different LoRa message sizes, will be considered.<br>
<br>
    Modified version from: http://www.lancaster.ac.uk/scc/sites/lora/lorasim.html <br>
    <br>
LoRaSim consist of one Python scripts: loraSim.py. All require the following packages: matplotlib, simpy and numpy

## Installation

Just git clone and run loraSim.py.

## Description

#### NODES
number of nodes to simulate.

#### AVGSEND
average sending interval in milliseconds(Message generation rate),include 300000ms,600000ms,1800000ms,3600000ms in the test.

#### EXPERIMENT
experiment is an integer that determines with what radio settings the simulation is run. 

##### 1
use the settings with the the slowest datarate (SF12, BW125, CR4/8).

##### 2
use the settings with the fastest data rate (SF6, BW500, CR4/5).

##### 3
use the settings as defined in LoRaWAN (SF12, BW125, CR4/5).

##### 4
optimise the setting per node based on link budget dynamic selection setting.

##### 5
similar to experiment 3, but also optimises the transmit power.

#### SIMTIME

total running time in milliseconds.

#### PAYLOAD

different load sizes (PL) available for testing,include 10,20,30,40,50,60,70,80,90,100.

#### COLLISION

set to 1 to enable the full collision check, 0 to use a simplified check (default). With the simplified check, two messages collide when they arrive at the same time, on the same frequency and spreading factor. The full collision check considers the two colliding message may still pass depending on the relative timing and difference in receive power.


### Output

The result of every simulation run will be appended to a file named expX.dat, whereby X is the experiment number. The file contains a space separated table of values for nodes, collisions, transmissions and total energy spent. <br>
<br>
The result of every simulation run will be appended to a file named exp-sendtimeX.txt, whereby X is the experiment number. The file contains a space separated table of values for nodes, collisions, payload and message generataion rate.<br>
<br>
The result of every simulation run will be appended to a file named exp-paylosdX.txt, whereby X is the experiment number. The file contains a space separated table of values for nodes, collisions, payload and toall transmissions.<br>
<br>
The data file can be easily plotted using e.g. gnuplot.

# License

LoRaSim - Copyright (c) 2016-2017 Thiemo Voigt and Martin Bor. This work is licensed under the Creative Commons Attribution 4.0 International License. To view a copy of this license, visit http://creativecommons.org/licenses/by/4.0/.





