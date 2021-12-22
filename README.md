# photon-threshold-ML
The minimum photon number that makes the sensation of seeing has been
investigated in the previous decades [1], [3], [4], [2]. The common method for
determining the minimum photon threshold number is doing experiments on
human subjects by sending their cornea a series of light flashes. After that,
the subjects are asked if they had any sensation of light or not. Answer of
this question is typically yes/no [1], [3]. Hecth et al showed that human are
able to see with the existence of minimum number of 5 − 7 photons.
The basic approach for determining the photon threshold number Hecth
et al is explained in the proceeding paragraphs.


![data](https://user-images.githubusercontent.com/51533525/147089120-2001ba22-c808-40c6-a7b3-8e988a9ac2c2.png)
Figure 1.1: Data for photon threshold experiment for three human subjects
by [1].


Each flash of light striking the cornea contains a mean photon number
given by Poisson distribution as in Eq 1.1. Retina can absorb no more than
10% [2], but the true portion is not known exactly. By keeping record of
yes/no answers, experimentalists obtain frequencies of seeing for each mean
photon number per flash. The table 1.1 contains the information as described
here for three subjects, and data of study by [1].

![Ekran Görüntüsü (73)](https://user-images.githubusercontent.com/51533525/147090881-b786c248-f718-49be-9e2d-3fc4e8b2edba.png)

![Ekran Görüntüsü (12)](https://user-images.githubusercontent.com/51533525/147091381-b0bfa932-2306-4a64-9c06-5268e51ef105.png)
Figure 1.2: Probability distributions for any average number of quanta absorbed by retina


Fig 1.2 indicates the cumulative distributions for any mean photon number n in Eq 1.1. For any average number of quanta per flash (n) , it gives
the probabilities that the flash will deliver to the retina n or more quanta,
depending on the value assumed for n. Experimental results of frequencies
of seeing data in Fig 1.1 for the three subjects are compared by cumulative
Poisson distributions in Fig 1.2. S.H., S.S. and M.H.P. are the initials of the
names of the subjects in the table in the Fig 1.1. The best fit line is found
as n = 6, 7, 5 for S.H., S.S., and M.H.P. respectively.


**Model**


**2.1 Modelling Photon Threshold Experiments with Machine Learning**

Photon threshold experiments with yes/no answers can be transformed into
a classification problem with machine learning.
We use machine learning package sckit-learn 0.23.1 in Python 3.7. We
use Logistic Regression model with hyper-tuned parameters C = 0.01 and
solver: ”liblinear”.
We generate random numbers n from Poisson distribution in Eq.1.1, with
a mean photon number n.
Let k be a threshold for the photons and the parameter y stands for the
yes/no answers. If the condition below is satisfied


![Ekran Görüntüsü (75)](https://user-images.githubusercontent.com/51533525/147091875-3b8f13aa-db94-4875-a8ba-598a1319d1e9.png)


than, we obtain an artificial data set for vision. We hold information of
frequency of seeing for each flash of light with a specific mean photon number
in this way. Machine learning methods are applied to this data in order to
predict frequency of seeing for a retina stroked by a flash of light with any
mean photon number.
For distributions with mean photon number n ≥ 2, we re-generate the
vision data for varying values of k = 2, 3, · · · , 9, and apply ML algorithm
separately for each data. By doing this, we aim to simulate the data for  different human subjects. We compare the simulation results for different
photon threshold numbers, (k)


**2.1.1 Results**

It is a good test bed for ML algorithm to use the data given for the three
subjects chosen from Table 1.1.


![Ekran Görüntüsü (78)](https://user-images.githubusercontent.com/51533525/147092276-148a9860-f1ac-4d85-bc88-04ea26c11e99.png)
![Ekran Görüntüsü (78)](https://user-images.githubusercontent.com/51533525/147092335-d910a683-8c77-495a-ae73-e22f2054ca9e.png)

Experimental values for the photon threshold number for the three people
are found by multiplying photon number that sent to their cornea by an
absorption factor. This is because of the fact that cornea can not absorb
all the photons striking it as discussed previously [2]. Another reason may
be due to the fact that the retina can not absorb all the photons passing
through cornea due to optical losses. These loss mechanism is also changes
from human to human.
For the human subjects in the experiment in Fig 1.1;
• S.H. : 3% of total quanta
• S.S. : 6% of total quanta
• M.H.P. : 3% of total quanta
gives the nearest fit to exact and experimental lines. We used only the first
serie of number of quanta and seeing frequency data in Table 1.1 for S.H.
and S.S.

