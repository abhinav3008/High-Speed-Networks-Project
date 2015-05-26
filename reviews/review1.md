
Project Review
=====================================================


## Overview

1) Briefly summarize the experiment in this project.
   The experiment seems to be well put together if there were no errors. For example, in:

   4.) c.) ii.) I do not know which component in Geni is the controller or switch.
                There was no Rspec file included to help me continue with the project.
				I went into their submission folder and continued with their submitted Rspecfile.
		   iii.) Step 2.) They forgot to include "apt-get" in their command instructions.
		         Step 5.) They did not include how to retrieve the controller-ip and if the arrows
			     should be included in the command. I used "ifconfig" to retrieve the IP.
	   v.) br0 needed to be established but wasn't, which prevented me from continuing the experiment.
	   The following lines are from my command history:

			dsj241@ovs:~/openvswitch-1.9.3$ sudo ovs-vsctl list-ports br0
			ovs-vsctl: no bridge named br0
			dsj241@ovs:~/openvswitch-1.9.3$ sudo ovs-vsctl set-controller br0 tcp:192.86.139.80:6633
			ovs-vsctl: no bridge named br0



2) Does the project generally follow the guidelines and parameters we have
learned in class?
-   Yes, it does. It specified how many components should be alotted for the experiments and explained
	which component is for what. The instructions were well laid out to help follow the flow of the
	experiment without any issues (besides the errors mentioned above). Because of the issues encountered,
	the experiment took more than 15 minutes (even incomplete).



## Experiment design

1) What is the goal of this experiment? Is it a focused, specific goal?
Is it useful and likely to have interesting results?
-   To show a comparitive analysis of Layer 2 and Layer 3 routing techniques
	on an Openflow network with a POX controller and three hosts connected
	to a single switch. These are configured to run as an OpenVswitch.
	There is a focused, specific goal and can achieve interesting results.

2) Are the metric(s) and parameters chosen appropriate for this
experiment goal? Does the experiment design clearly support the experiment goal?
-   The metric(s) and parameters chosen for this experiment are approriate
	and the design supports the experiment goal.


3) Is the experiment well designed to obtain maximum information with the
minimum number of trials?
-   It is well designed and provides enough information with an ideal
	number of trials.


4) Are the metrics selected for study the *right* metrics? Are they clear,
unambiguous, and likely to lead to correct conclusions? Are there other
metrics that might have been better suited for this experiment?
-   The metrics selected are the right metrics to analyze. Ping tests
	were conducted but seem to be extensive.

5) Are the parameters of the experiment meaningful? Are the ranges
over which parameters vary meaningful and representative?
-   The parameters are meaningful. The ranges are meaningful and
	representative, but as mententioned in 4.), could be minimized.

6) Have the authors sufficiently addressed the possibility of interactions
between parameters?
-   The authors have sufficiently addressed the possibility of interactions
	between parameters.


7) Are comparisons made reasonably? Is the baseline selected for comparison appropriate
and realistic?
-   The comparisons are reasonable. There was no baseline for comparison.


## Communicating results


1) Do the authors report the quantitative results of their experiment?
-   Yes they do.

2) Is there information given about the variation and/or distribution of
experimental results?
-   Yes, tables are provided.

3) Do the authors practice *data integrity* - telling the truth about their data,
avoiding ratio games and other practices to artificially make their results seem better?
-   Yes, all of the data provided is actual data retrieved from their experiment.

4) Is the data presented in a clear and effective way? If the data is presented in
graphical form, is the type of graph selected appropriate for the "story" that
the data is telling?
-   The graphs shown are appropriate for the experiment.

5) Are the conclusions drawn by the authors sufficiently supported by the
experiment results?
-   Yes.

## Reproducible research



1) Did the authors include instructions for reproducing the experiment in 3 ways (Raw data -> Results,
Existing experiment setup -> Data, and Set up experiment)? Are the instructions clear
and easy to understand?
-   For the most part, the experiment is easy to follow and the 3 ways are utilized. The only
	issues are the ones mentioned above.

2) Were you able to successfully produce experiment results?
-	No.

3) How long did it take you to run this experiment, from start to finish?
-	I could not complete the experiment.

4) Did you need to make any changes or do any additional steps beyond the documentation in order to successfully complete this experiment? Describe *in detail*. How long did these extra steps or changes take to figure out?
-	Yes, these have been mentioned earlier.
	1.) A command was left out which left me confused for about 5 minutes before realizing the extra command I needed.
	2.) The controller-ip wasn't explained.
	3.) Rspec data was no included (had to use their Rspec)
	4.) br0 could not be established. I ended my experiment there.

5) In the [lecture on reproducible experiments](http://witestlab.poly.edu/~ffund/el6383/files/Reproducible+experiments.pdf), we mentioned six degrees of reproducibility. How would you characterize this experiment - where does it fall on the six degrees of reproducibility?
-	3. The results can be reproduced by an independent researcher, requiring considerable effort.


## Other comments to authors

Please write any other comments that you think might help the authors
of this project improve their experiment.

-	I would go through the experiment by using the guide provided and update any information left out.
