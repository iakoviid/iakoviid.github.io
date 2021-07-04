---
layout: post
title: A mathematical theory for Occam's razor
---


Simplicity is often one of the main goals of any learning process. If a theory that explains a phenomenon is simple then we can understand it more quickly and use it more efficiently. Additionally, it is also believed that simpler models are probably more credible. That belief, Occam’s razor principle, has greatly influenced scientific thinking as a heuristic and it is applied frequently in the field of Data Science. Occam’s original statement is often interpreted as follows: all other things being equal, the simplest explanation of the observations is more likely to be true. Although this statement is qualitative in nature, there are mathematically quantifiable statements that attempt to capture the meaning of this heuristic. However, as of today there does not exist a single unifying theory that can explain all of its occurrences. With this essay we will present the results of some candidate theories as well as their shortcomings.

To properly quantify this statement we must first of all choose a notion of simplicity or, equivalently, complexity. There are many notions of complexity, like the Vapnik–Chervonenkis (VC) dimension, Rademacher Complexity, Kolmogorov Complexity and Description length, that have been formally studied in mathematics and are used in the field of data science to prove theoretical guarantees. Using properties of these notions, we can derive probabilistic upper bounds regarding the actual, test error of a model using the training error and a notion of complexity, called generalization bounds [1]. These bounds usually imply that using a space of more complex functions, with higher capacity, might lead us to a model with a higher generalization error than a more simple space of functions with lower capacity. Furthermore, by minimizing an upper bound on the generalization error, or expressions that increase with it, we can formulate a mathematically justifiable model search and selection principle which is less susceptible to overfitting, this technique is called structural risk minimization [2].

The originally intended use of the Occam’s razor principle was model selection. Model selection can be done formally in this manner using the Minimum Description Length principle (MDL) [3]. This principle proposes that we choose the hypothesis that gives us the smallest description length for the data. In a way, this is a literal application of the Occam's Razor principle. Like in the case of structural risk minimization, MDL results in the minimization of an error term plus a complexity term, to account for larger models. One of the most notable benefits of MDL is its strong connection with the Maximum Likelihood Estimation (MLE), which is one of the most natural and important forms of estimation in statistics. In fact, MDL can be interpreted as a generalization of MLE that can be applied almost universally and not just for single parametric families. Moreover, this theory has very attractive proven convergence properties, like consistency, that are in some cases even better than Bayessian Inference results [4]. The applications of MDL exceed beyond the confines of model selection to parameter estimation and prediction.

Furthermore, Occam's razor like statements have also been used in other areas of computational learning theory for constructing necessary and sufficient conditions for the membership of a problem in the class of Probably Approximately Correct (PAC) learnable problems. Specifically, it has been proven that the existence of a polynomial time consistent Learning Algorithm that outputs simple hypotheses implies that the concept class is PAC-learnable [5], [6]. Simplicity in this context implies a parametric bound on the representation of the output hypothesis or on the VC dimension of the set of different outputs. Under mild conditions, this statement can also be sufficient [7]. This leads to a different characterization of the PAC-learnability of many popular concept classes. Results like these are very important as they can lead to more systematic proofs of PAC-learnability and different techniques in learning algorithm design that use complexity criteria.


Even though the statements and theories presented above are sound, they do not produce valuable results in an overparameterized setting, i.e. when the number of parameters is bigger than the number of training samples. In these situations, we have the occurrence of the double descent phenomenon [8]. Although, classical generalization bounds become large and not meaningful and as a result they do not explain the effectiveness of high dimensional models such as deep neural networks (DNNs). Different methods should be developed not only for model selection and design but also to complete our theoretical understanding in these situations. Here we have another version of the Occam’s Razor principle that is more useful and prevalent: All other things being equal, in terms of empirical loss, the smoothest model is preferable. The smoothest estimator in this context is the one that minimizes a functional norm. Upper bounds can be found in order to relate the generalization error of an interpolation process and its functional norms [9], [10], [11]. Also, the previously mentioned older versions of this principle can be reformulated to become more useful in this setting. For example, traditional generalization bounds have become tighter with the use of compression schemes [12] and MDL ideas have been used to define notions of complexity that for some high dimensional models scale logarithmically with the number of parameters instead of linearly [13].


In conclusion, identifying when overfitting is present and avoiding it is one of the most important problems in Machine Learning. The idea of Occam’s Razor is very tightly connected with this problem, and has been greatly influencing machine learning theory in the last century with its basis on a theory of capacity control. Although this concept is central and intuitive there is a disconnect between theory and practice regarding the overparameterized regime. At this moment, there does not exist a single unifying theory that can be applied to all cases. The generalization of this concept to a single mathematical theory of Occam’s Razor is one of the main open problems in Mathematical Data Science today and solving it will greatly increase our understanding of the field.

References:

[1] Vapnik V.: The Nature of Statistical Learning Theory

[2] Vapnik V.: Principles of Risk Minimization for Learning Theory

[3] P. D. Grünwald: The minimum description length principle

[4] Yuhong Yang and Andrew R. Barron: An Asymptotic Property of Model Selection Criteria

[5] Blumer A., Ehrenfeucht A., Haussler D. and Warmuth M. K.: Occam’s razor

[6] Blumer A., Ehrenfeucht A., Haussler D., Warmuth M. K and Haussler D.: Learnability and the Vapnik-Chervonenkis Dimension

[7] Raymond Board and Leonard Pitt: On the necessity of Occam algorithms*

[8] Mikhail Belkin, Daniel Hsu, Siyuan Ma and Soumik Mandal: Reconciling modern machine-learning practice and the classical bias–variance trade-off

[9] Henning Petzka, Michael Kamp, Linara Adilova, Mario Boley, Cristian Sminchisescu: Relative Flatness and Generalization in the Interpolation Regime

[10] Geoffrey Chinot, Matthias Loffler and Sara van de Geer: On the robustness of minimum-norm interpolators

[11] Mikhail Belkin, Daniel Hsu and Partha P. Mitra: Overfitting or perfect fitting? Risk bounds for classification and regression rules that interpolate

[12] S. Arora, R. Ge, B. Neyshabur, and Y. Zhang: Stronger generalization bounds for deep nets via compression approach.

[13] Raaz Dwivedi, Chandan Singh, Bin Yu and Martin. J. Wainwright: Revisiting complexity and the bias-variance tradeoff
