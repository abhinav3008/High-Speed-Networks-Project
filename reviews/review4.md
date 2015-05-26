Project Review
=====================================================

## Overview

**1) Briefly summarize the experiment in this project.**

This experiment trys to compare RTT distribution time and throughput of Layer 2 and Layer 3 routing techniques on an OpenFlow network with a POX controller and three hosts connected to a single switch which is configured to run as an Open vSwitch.

**2) Does the project generally follow the guidelines and parameters we have learned in class?**

Yes. Its goal is clear and useful, which is to compare RTT and throughput between Layer 2 switching and Layer 3 switching on a simple OpenFlow network. And the chosen parameters and metrics are representative for archiving this goal.

## Experiment design

**1) What is the goal of this experiment? Is it a focused, specific goal? Is it useful and likely to have interesting results?**

The goal of this experiment is to compare RTT and throughput between Layer 2 switching and Layer 3 switching on a simple OpenFlow network with single controller and three hosts connected to a switch. A Layer 3 learning switch functions like a Layer 2 learning switch, except with IP addresses rather than MAC addresses, and some ARP packet construction logic. Layer 3 switches are usually faster than Layer 2 switches. This experiment can verify this in some ways.

**2) Are the metric(s) and parameters chosen appropriate for this experiment goal? Does the experiment design clearly support the experiment goal?**

The metrics (RTT and throughput) and parameter (Layer 2 switching or Layer 3 switching) are appropriate for the goal. But the experiment design only suits for measuring RTT. Because it is relatively complicated to set up a scenario which has enough flow setup processes in every second to affect the actual throughput.

**3) Is the experiment well designed to obtain maximum information with the minimum number of trials?**

The experiment only needs to make several trials to get enough RTT values for analysis. But there has some difference between the sample sizes of two cases, Layer 2 learning switch or Layer 3 learning switch. The sample sizes should be the same in order to avoid ratio games when the goal is to measure the accurate difference.

The authors did not make use of throughput under the setup of this experiment. Throughput seems to be useless since there is no obvious difference between two cases.

**4) Are the metrics selected for study the *right* metrics? Are they clear, unambiguous, and likely to lead to correct conclusions? Are there other metrics that might have been better suited for this experiment?**

The metrics are the right ones since the goal of this experiment exactly is to compare RTT and throughput between Layer 2 switching and Layer 3 switching. However, throughput is not so useful under the setup of the experiment.

**5) Are the parameters of the experiment meaningful? Are the ranges over which parameters vary meaningful and representative?**

The parameter of the experiment is meaningful. A Layer 3 learning switch functions like a Layer 2 learning switch, except with IP addresses rather than MAC addresses, and some ARP packet construction logic. So there may exist a slightl difference between two switching modes.

**6) Have the authors sufficiently addressed the possibility of interactions between parameters?**

The authors did not address the possibility of measured differences between parameter. They only mentioned the reason for the obvious larger RTT of the first ICMP packet under two cases.

The other interactions the authors did not make explanation:

* The RTT of Layer 3 learning mode is slightly larger than the RTT of Layer 2 learning mode within first one or two ICMP packet.

* There are two obviously larger RTTs under the Layer 3 learning mode, while under the Layer 2 learning mode there has only one RTT obviously larger than the others.

**7) Are comparisons made reasonably? Is the baseline selected for comparison appropriate and realistic?**

The authors made a reasonable comparison between parameter. They ploted RTT distribution of ICMP sequence number, which showed the change of RTT under two cases. But I think they should also make an comparison between the accurate mean RTT values of every first ICMP packet under two cases. This could show the difference of flow setup performance of Layer 2 switching and Layer 3 switching.

## Communicating results

**1) Do the authors report the quantitative results of their experiment?**

The authors mentioned a part of their quantitative results. The others are in the submit folder as raw files.

**2) Is there information given about the variation and/or distribution of experimental results?**

The authors made an explanation for extra latency imposed by flow setup. But they did not explain the difference of extra latency of two cases, which is the key point of this experiment.

**3) Do the authors practice *data integrity* - telling the truth about their data, avoiding ratio games and other practices to artificially make their results seem better?**

Yes, the authors made a good practice of data integrity.

**4) Is the data presented in a clear and effective way? If the data is presented in graphical form, is the type of graph selected appropriate for the "story" that the data is telling?**

Yes, the authors presented the data using six plots. Three of them showed the RTT distribution of the ICMP sequence number, which made a good demonstration of the actual difference between L2 learning mode and L3 learning mode.

**5) Are the conclusions drawn by the authors sufficiently supported by the experiment results?**

The authors only presented the difference they found but did not made an explanation for it.

## Reproducible research

**1) Did the authors include instructions for reproducing the experiment in 3 ways (Raw data -> Results, Existing experiment setup -> Data, and Set up experiment)? Are the instructions clear and easy to understand?**

The authors only introduce a rough procedure for data analysis without any instructions for setting up data analysis environment. I have to refer to the steps in lab2b to install R Studio.

And the authors did not provide their hostnames or ports for logging into each machine. Thus I cannot access to the existing setup on GENI.

The instructions for setting up experiment are provided but not quite clear or explicit. I need to do some extra steps in order to complete the setup.

**2) Were you able to successfully produce experiment results?**

I failed to reproduce the experiment results neither by following the given tutorial nor with my efforts to find the other necessary steps. I can only produce the `ping` results of Layer 2 switching and the plots of them, and a modified version of Layer 3 switching example.

**3) How long did it take you to run this experiment, from start to finish?**

I spent 8 hours in the first day and several more hours in the second day in order to reproduce this experiment, but I only completed an modified version of this experiment. I could not complete the Layer 3 switching part exactly same with the experiment needed. The hosts could not `ping` each other after executing all the setting steps in the tutorial.

**4) Did you need to make any changes or do any additional steps beyond the documentation in order to successfully complete this experiment? Describe *in detail*. How long did these extra steps or changes take to figure out?**

The given documents are not sufficient to complete the experiment.

* There are some missing steps in Step v of part c. The authors only listed the configuration steps for one of three bridges. And they also mixed up the different names of the bridges, which will lead to some errors during setup.

* The RSpec file for Layer 3 switching topology is not provided. I found a 2-host version from the Wiki page linked in the tutorial and modified it to a 3-host version as needed by the experiment.

* I could not `ping` to each other under Layer 3 switching mode with the given configuration steps. So I tried to set the 3 hosts in the same subnet and to use only one OVS bridge, and I succeed to get ping outputs with this setup.

* The detailed procedure for setting up R Studio is not provided. I refered to the steps in lab2b.

* The detailed procedure for uploading output files to Bitbucket is not provided in the tutorial.

It cost me about 5 hours to study the whole experiment's setup in order to figure out these extra steps and changes.

**5) In the [lecture on reproducible experiments](http://witestlab.poly.edu/~ffund/el6383/files/Reproducible+experiments.pdf), we mentioned six degrees of reproducibility. How would you characterize this experiment - where does it fall on the six degrees of reproducibility?**

I think this experiment has a degree between 2 and 3.

## Other comments to authors

**Please write any other comments that you think might help the authors of this project improve their experiment.**

* This experiment uses an old version (v1.9.3) of Open vSwitch, while it actually could be pre-installed with a newer version (v2.3.1) if we use the provided RSpec in GENI, thus the configuration steps for OVS could be skipped.

* In the Layer 3 learning switch configuration part, there are six commands for inserting flows with OVS itself. But I think they are unnecessary. Since the purpose of the experiment is to test the performance of flow setup by a controller, there is no need to pre-configure the OVS to let it know how to forward the new flow. Furthermore, the flow table we inserted into the OVS will be deleted right after the OVS connected to the controller. So I think we can skip these steps.
