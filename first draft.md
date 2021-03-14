**<center> <font size=5 face="Times New Roman" > Review：Sequential exploration in the Iowa gambling task: Validation of a new computational model in a large dataset of young and old healthy participants <center></font>**
    <center><font size=3 face="Times New Roman" > Shen Xu<sup>1</sup><center>
        <font size=3 face="Times New Roman" >1. School of Psychological and Cognitive Sciences, Peking University, Beijing 100871, China </font>
        </br></br>
        **<p align="left"><font size=5 face="Times New Roman" >*Abstract*</p>**
        <p align="left"><font size=4 face="Times New Roman" >This article mainly discusses a paper published by Romain Ligneul in the journal PLOS COMPUTATIONAL BIOLOGY in 2019. The author proposed a new computational model for the Iowa gambling task (IGT). One of the most common examples of the Iowa Gambling Task used to assess decision-making and executive function in neurological and mental illnesses. The author believes that the subjects have exploratory behaviors when doing IGT, so he proposed a Value plus Sequential Exploration model (VSE). Parameter recovery, model recovery and simulation analyses confirmed the superiority of the VSE scheme.</font>  
    **<p align="left"><font size=5 face="Times New Roman" >*Iowa gambling task (IGT)*</p>**
<p align="left"><font size=4 face="Times New Roman" >In the IGT, participants must sample 4 decks of card associated with gains and losses whose magnitudes vary in a probabilistic manner. Unbeknownst to participants, decks C and D are advantageous despite offering smaller gains, because the losses are respectively very low or rarely encountered. The columns below each deck report the empirical minimum, maximum and average magnitude of gains (all decks have a 100% gain probability), the frequency, maximum and mean magnitude of losses, as well as the overall expected value (see Figure 1).
</br><center><img src="https://github.com/xushenpsy/picture1/blob/main/adada.png?raw=true" width = "400" height = "600" alt="" align=center />  
</br> 
<font size=3 face="Times New Roman" >Figure 1. Iowa gambling task</font>

**<p align="left"><font size=5 face="Times New Roman" >*Value plus Sequential Exploration (VSE) model*</p>**
<p align="left"><font size=4 face="Times New Roman" >On each trial, the exploitation weight of each desk d is updated according to the following equations:  
<script type="text/javascript" src="http://cdn.mathjax.org/mathjax/latest/MathJax.js?config=default"></script>
$$Exploit_i(t+1)=Exploit_i(t)*△+v(t)\tag{1}$$  
    
$$Exploit_i(t+1)=Exploit_i(t)*△\tag{2}$$
<p align="left"><font size=4 face="Times New Roman" >Equation (1) represents the exploitation value of the deck chosen. Equation (2) represents the exploitation value of the deck unchosen, where $△$ denotes the decay parameter (from 0 to 1),$v(t)=Gain(t)^\theta-Loss(t)^\theta$ and $i=1, 2, 3, 4$.
<p align="left"><font size=4 face="Times New Roman" >For the exploration behavior, the weight is controlled by the following equations:
$$Explore_i(t+1)=0\tag{3}$$
    
$$Explore_i(t+1)=Explore_i(t)+\alpha*(\varphi-Explore_i(t))\tag{4}$$
Equation (3) represents the exploration value of the deck chosen. Equation (4) represents the exploration value of the deck unchosen. $\alpha$ is the learning rate. $\varphi$ is the free parameter representing “exploration bonus” which is unbounded.  
<p align="left"><font size=4 face="Times New Roman" >Based on the above exploitation behavior and exploration behavior, the probability of each deck being selected is expressed by the softmax function as:
    
$$P(Choice=i)=\frac{e^{(Explore_i+Exploit_i)*\beta}}{\sum_{k=1}^{4}{e^{(Explore_k+Exploit_k)*\beta}}}$$ 
**<p align="left"><font size=5 face="Times New Roman" >*Model comparison*</p>**
<p align="left"><font size=4 face="Times New Roman" >The comparison of the VSE architecture with the 5 alternative models was performed by Romain Ligneul using the 504 subjects dataset. Model fit index: Bayesian Information Criterion (BIC), Akaike Information Criterion (AIC) and Free energy (F) all support the superiority of the VSE model (see Figure 2)
</br><center><img src="https://github.com/xushenpsy/picture1/blob/main/22.png?raw=true" width = "400" height = "600" alt="" align=center />  
</br> 
<font size=3 face="Times New Roman" >Figure 2. Model comparison</font>  
    
**<p align="left"><font size=5 face="Times New Roman" >*Disscussion*</p>**
<p align="left"><font size=4 face="Times New Roman" >Combining the content of the entire article, I think this computational modeling article belongs to the second category: Propose a new model as a new hypothesis or as a quantification of the original hypothesis in the field, and test different hypotheses by comparing the degree of fit between different models and data.

