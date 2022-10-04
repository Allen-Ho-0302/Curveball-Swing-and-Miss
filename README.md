# Curveball-Swing-and-Miss  
Create a model to evaluate pitcher’s ability to generate swing and miss(whiff) with curveballs.  

# Objective  
Create a model to evaluate pitcher’s ability to generate swing and miss(whiff) with curveballs.  

# Range of the Dataset  
2083 CBs thrown by the Braves’ pitchers in 2018 and 2019 (not completely true data).  

# Types of inputs  
Pitcher_Throws: The pitcher’s handedness  
Batter_Hits: The batter’s handedness  
release_speed: The pitch’s velocity (mph)  
x_movement: The pitch’s horizontal movement (inches)  
z_movement: The pitch’s vertical movement (inches)  
release_spin_rate: The pitch’s spin rate (rpm)  
spin_dir: The pitch’s spin axis (degrees)  
release_pos_x: The horizontal release point for that pitch (ft)  
release_pos_z: The vertical release point for that pitch (ft)  
release_extension: The release extension for that pitch (ft)  
plate_x: The horizontal location of the ball when it crosses home plate (ft)  
plate_z: The vertical location of the ball when it crosses home plate (ft)  
There are also a few context features like innings, strikes, runners, outs in this dataset. However, in this project we will focus more on the above features first.  

# Steps  
Data Preprocessing  
Exploratory Data Analysis  
Initial Logistic Regression Models  
    Model 1: if the CB will generate a whiff based on the features given  
    Model 2: if the CB will generate a whiff given that the batter swings at the pitch based on the features given  
GAM Models  
    GAM with Interaction between Smoothed and Factor Variables  
    GAM with Interaction between Smoothed Variables  
    Calibration Plot  
    SMAA and Split Half Correlation  
Random Forest and XGBoost Models  
CB Swing and Miss True Talent  
Mixed Model  
Takeaways  
Limitations and Potential Future Steps  

# Takeaways  
From nearly all of the models, plate location contributes a lot to the prediction of a curveball generating swing and miss or not.  
Generally, throwing at the lower part of the strike zone or even lower than the strike zone vertically and throwing close to the left handed batter side horizontally could generate more whiffs.  
LHP throwing further down and out against RHB could have surprising good effect in generating swing and misses.  
Who the pitcher is affects how strong this phenomenon is. We can see the true talent for this “skill” for the pitchers in the dataset in the leaderboard. However, the sample size is small here. More instances should give us more confidence in this.  

# Some Limitations and Potential Future Steps  
CBs could be less effective at generating swing and misses than say SLs, so maybe it is more important for some pitchers to be able to locate that pitch in the zone. Focusing on the swing and miss of curveballs could be misleading since in some cases pitchers probably aren’t really trying to get a swing and miss, they’re only trying to loop that thing in the zone for a called first strike.  
Add more instances to the dataset.  
Add more predictors to gam or mixed model and more explorations/visualizations  
More All encompassing models (Random forest, XGB) and Interpretation  
    Global Model-Agnostic Methods  
        The partial dependence plot  
        Accumulated local effect plots  
        Permutation feature importance  
    Local Model-Agnostic Methods  
        Individual conditional expectation curves  
        Local surrogate models (LIME)  
        Counterfactual explanations  
        Shapley values  
