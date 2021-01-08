## Solar flare prediction with Deep Neural Networks (DNN)

**Project description:** Three different deep learning architectures were trained and optimized to predict the likelihood 
of a flare erupting from a sunspot, that is larger than a class M5.0, within the next 24 hours. 
The architectures used are: MLP, TCN and LSTM.
The [dataset](https://github.com/JasonTLWang/LSTM-flare-prediction) used is open source and compiled by Liu et al.
The data contains image derived parameters called [SHARP](http://jsoc.stanford.edu/doc/data/hmi/sharp/sharp.htm), 
which are physics-based equations obtained from the solar images.

### 1. Obtaining the data
Our own [data acquisition pipeline](https://github.com/Dewald928/DeepFlarePred/blob/master/Test_Scripts/data_aquisition_pipeline.ipynb) was developed
to download the SHARP data. The SHARP data is derived from the magnetogram images (as shown).

<img src="../flare_prediction/magnetogram.jpg?raw=true"/>

### 2. Optimizing the models
The different models were trained and optimized with the help of "[Weights and Biases](https://wandb.ai/home)". 
After extensive experimenting we selected our best models to test on the "held-out" data.

<img src="../flare_prediction/wandb.png?raw=true"/>

### 3. Testing
We tested for various metrics, most prominently the True Skill Statistic (TSS).
Our models were investigated with multiple evaluation plots.

<img src="../flare_prediction/PP_NOAA_12017.pdf?raw=true"/>

### 4. Deployment
As a proof of concept, we deployed our model in a near-realtime setting by using the MLP model.

The model is live at: [http://deep-flare-prediction.herokuapp.com/](http://deep-flare-prediction.herokuapp.com/).

