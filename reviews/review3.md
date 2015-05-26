
Project Review
=====================================================

## Overview

1) Briefly summarize the experiment in this project.
Ans: The project aims at parsing the RTT and throughput between L2 and L3 switching on a network topology consisting of an OVS switch connected to three hosts
and a controller.

2) Does the project generally follow the guidelines and parameters we have
learned in class?
Ans: It does not have a defined goal as to what the aauthor is trying to draw from the results.


## Experiment design

1) What is the goal of this experiment? Is it a focused, specific goal?
Is it useful and likely to have interesting results?
Ans: The goal is to see the effect on the time the controller takes to process the packets when it is run in different modes i.e L2 and L3 Learning mode. Yes, it has
interesting results.

2) Are the metric(s) and parameters chosen appropriate for this
experiment goal? Does the experiment design clearly support the experiment goal?
Ans:Yes

3) Is the experiment well designed to obtain maximum information with the
minimum number of trials?
Ans: Yes

4) Are the metrics selected for study the *right* metrics? Are they clear,
unambiguous, and likely to lead to correct conclusions? Are there other
metrics that might have been better suited for this experiment?
Ans: Yes, the metrics chosen are appropriate.

5) Are the parameters of the experiment meaningful? Are the ranges
over which parameters vary meaningful and representative?
Ans: Yes

6) Have the authors sufficiently addressed the possibility of interactions
between parameters?
Ans: They have shown the affect on RTT but have not mentioned anything about the throughput.


7) Are comparisons made reasonably? Is the baseline selected for comparison appropriate
and realistic?
Ans: Yes the author has kept the same environment for both the controller modes.


## Communicating results


1) Do the authors report the quantitative results of their experiment?
Ans: Yes they do for RTT, but not for throughput.

2) Is there information given about the variation and/or distribution of
experimental results?
Ans: Yes they have plotted a graph.

3) Do the authors practice *data integrity* - telling the truth about their data,
avoiding ratio games and other practices to artificially make their results seem better?
Ans: No

4) Is the data presented in a clear and effective way? If the data is presented in
graphical form, is the type of graph selected appropriate for the "story" that
the data is telling?
Ans: Yes

5) Are the conclusions drawn by the authors sufficiently supported by the
experiment results?
Ans:Yes the graph supports the conclusions the authors have drawn.
## Reproducible research



1) Did the authors include instructions for reproducing the experiment in 3 ways (Raw data -> Results,
Existing experiment setup -> Data, and Set up experiment)? Are the instructions clear
and easy to understand?
Ans: Yes they did but the commands were faulty at some places and the instructions were not as clear as they could have been.

2) Were you able to successfully produce experiment results?
Ans: No, was unable to get the ping to work even after following the exact instructions.

3) How long did it take you to run this experiment, from start to finish?
Ans: I had put in 5 hours but was unable to get the results.

4) Did you need to make any changes or do any additional steps beyond the documentation in order to successfully complete this experiment? Describe *in detail*. How long did these extra steps or changes take to figure out?
Ans: I had to alter some commands and even explore the internet for some parts.

5) In the [lecture on reproducible experiments](http://witestlab.poly.edu/~ffund/el6383/files/Reproducible+experiments.pdf), we mentioned six degrees of reproducibility. How would you characterize this experiment - where does it fall on the six degrees of reproducibility?
Ans: 2


## Other comments to authors

Please write any other comments that you think might help the authors
of this project improve their experiment.

The commands to configure the OVS switch has OVSbr1 in some places and br0 in some. Also you did not mention the resource I had to reserve regarding the switch:
is it OVS switch or a normal switch.
