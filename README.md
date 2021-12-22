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


Model
2.1 Modelling Photon Threshold Experiments
with Machine Learning
Photon threshold experiments with yes/no answers can be transformed into
a classification problem with machine learning.
We use machine learning package sckit-learn 0.23.1 in Python 3.7. We
use Logistic Regression model with hyper-tuned parameters C = 0.01 and
solver: ”liblinear”.
We generate random numbers n from Poisson distribution in Eq.1.1, with
a mean photon number n.
Let k be a threshold for the photons and the parameter y stands for the
yes/no answers. If the condition below is satisfied
