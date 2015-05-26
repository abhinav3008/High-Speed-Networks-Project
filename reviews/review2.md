
Project Review
=====================================================

## Overview

1) Briefly summarize the experiment in this project.

A:
First of all, configure the switch to work as an OpenVswitch and configure the controller to run as a POX controller.
Then run the controller in L2 learning mode and L3 learning mode respectively, log into the hosts to ping each other and save the ping output.
The experiment is expected draw the comparitative analysis of Layer 2 and Layer 3 routing techniques.

2) Does the project generally follow the guidelines and parameters we have
learned in class?

A:
Mostly, the author followed the guidelines, the author had state their aim and mentioned to study L2 and L3 learning mode, choosed to measure RTT as the metric,
but did not mention what parameters may affect the experiment.

## Experiment design

1) What is the goal of this experiment? Is it a focused, specific goal?
Is it useful and likely to have interesting results?

A:
The goal of the experiment is to build an Openflow network topology one with POX controller on a slice and the other slice with multiple hosts
connected to a single switch. Show that the Openflow Network is active and working from ping results and calculate the throughput between every
two hosts and plot the results (RTT) against ICMP Seq number.
The goal is focused, but it do not seem to have a interesting result, in the author's statement, the author just want to do a plot but without analysing it,
which is not likely to get some meaningful result(in the report, the author indeed did not do any analysing, just gave the plot)

2) Are the metric(s) and parameters chosen appropriate for this
experiment goal? Does the experiment design clearly support the experiment goal?
A:
Yes, the author want to study RTT and choose RTT to measure;
Yes, the author set the switch to run in two different mode and measured RTT.

3) Is the experiment well designed to obtain maximum information with the
minimum number of trials?

A: Hard to answer, the experiment do not need much information, in fact, the author just designed 2 trails.

4) Are the metrics selected for study the *right* metrics? Are they clear,
unambiguous, and likely to lead to correct conclusions? Are there other
metrics that might have been better suited for this experiment?
A:
Yes, it is the right metric and it is clear;
No better choice, the aim of the experiment is to measure RTT, then RTT will be the best metric with no doubt

5) Are the parameters of the experiment meaningful? Are the ranges
over which parameters vary meaningful and representative?

A: Yes, RTT is an important and metric in measuring the performance of a switch.

6) Have the authors sufficiently addressed the possibility of interactions
between parameters?

A: No.


7) Are comparisons made reasonably? Is the baseline selected for comparison appropriate
and realistic?

A: Yes, the author compared the RTT between two switch running in different modes.
I don't think so, in the result, RTT changes along with ICMP Seq number, the auther did not explain why; And the author did not explain the difference
in performance between the two switchs running in different modes.

## Communicating results


1) Do the authors report the quantitative results of their experiment?

A: The auhtor submit some graph in submit folder, but I think the author should give some analyse and explanaiton of the charts.

2) Is there information given about the variation and/or distribution of
experimental results?
A: No

3) Do the authors practice *data integrity* - telling the truth about their data,
avoiding ratio games and other practices to artificially make their results seem better?

A: The author did not analyse the data

4) Is the data presented in a clear and effective way? If the data is presented in
graphical form, is the type of graph selected appropriate for the "story" that
the data is telling?

A: Yes, the author record ping output, it is clear.
The author did line plot, it is suitable when comparing numerical metric.

5) Are the conclusions drawn by the authors sufficiently supported by the
experiment results?

A: There's no apparent conclusion.

## Reproducible research



1) Did the authors include instructions for reproducing the experiment in 3 ways (Raw data -> Results,
Existing experiment setup -> Data, and Set up experiment)? Are the instructions clear
and easy to understand?

A: Yes, the authors include instructions for reproducing the experiment in 3 ways
It is not very clear, in 'Raw data -> Results' part, the author gave almost no instruction, but since we have done similar experiments before, it's reproducible
BUT, in 'Existing experiment setup -> Data' part, the author DID NOT give the link to use the existing materials.
In 'Set up experiment' part, i failed to reproduce the experiment.
2) Were you able to successfully produce experiment results?

A:
By using the existing raw data, i can reproduce the experiment, but i can not reproduce the experiment in the other two ways.
As I have mentioned in last question, the author did not give us the link to log into their configured experiment setup, so there's no way to finish the
experiment in this way.
When I tried to set up a experiment by myself, I met lots of problems:
The author submit the configuration file for l3 lenrning switch but not the l2's, so i tried the l3 switch configuration file and anothor configuration file in
the submit folder to move on, but failed, i tried to do some change and googled to solve some other problems, however, it did not run as the experiment expected.
Also in l3 experiment.
3) How long did it take you to run this experiment, from start to finish?

A:
more than 10 hours

4) Did you need to make any changes or do any additional steps beyond the documentation in order to successfully complete this experiment? Describe *in detail*. How long did these extra steps or changes take to figure out?
Yes,
fist of all, the author just offered l3 switch configuration file but not the l2's, so i got struck in configuring the switch to run in l2 learning mode,
in 'step v--View port configuration', it showed no such bridge, so i tried to add a bridge named 'br0' to move on the experiment;
however, there's something wrong, in step vi, the author did not mention whitch interfece to use
when i used eth0's IP and tried to ping, it's working, but as the author mentioned, ping should not work at this time
when i used eth1's IP and tried to ping, it's not working as the author mentioned, but after doing 'vii.Run the controller in L2 learning mode',
ping was still not working while the author says that it should work.
so i did not get meaningful ping outputs.

5) In the [lecture on reproducible experiments](http://witestlab.poly.edu/~ffund/el6383/files/Reproducible+experiments.pdf), we mentioned six degrees of reproducibility. How would you characterize this experiment - where does it fall on the six degrees of reproducibility?
I think it should be 3 or less, the major problem is that the author did not give us enough crucial materials(maybe just forget), so base on the instruction,
we may need to write a configuration file of l2 learning mode switch, maybe it is not a difficult task for a experienced researcher or someone who has done
similar configuration before, but since i am none of them, it is almost impossible for me.


## Other comments to authors

Please write any other comments that you think might help the authors
of this project improve their experiment.
