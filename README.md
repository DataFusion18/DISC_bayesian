## Notre Dame REU: Project 2

This is a repository for a Bayesian Poisson point process model we are recreating from a paper written by Malcolm Itter. Malcolm Itter is a PhD candidate at Michigan State University studying forest demographic processes. Read more about his work <a href= "https://www.mitter-forestecology.com/about.html">here</a>.

The Bayesian model attempts to predict local fires surrounding lakes by investigating charcoal counts from the past as an indicator of a regional or local fire. The Poisson process is a fitting addition to the model given the use of charcoal counts. With that being said, the original model was developed on the notion that charcoal data could be separated into a background and a foreground where the background represents regional fire noise and the foreground represents peak charcoal amounts that are caused by a local fire. This idea held true in Alaskan lakes, but now we are interested as to whether or not this is the case with lakes residing in the Midwest. We have 18 lakes of interest that we will model separately first and then, jointly.

Read through the walkthrough of our code and processes in the <a href="https://github.com/adraper2/DISC_bayesian/blob/master/walkthrough.Rmd">walkthrough.Rmd</a> file.

### General Steps to Running this Model
* Step 1: Setup and Variable Manipulations
* Step 2: Approximate Background and Foreground Intensities
* Step 3: Setup Intial Values and Generalized Additive Models
* Step 4: Create Holdout Step for Cross-validation
* Step 5: Cross-validate Model against Holdout Set
* Step 6a: Setup Priors and Inputs for second Cross-validation
* Step 6b: Run Markov chain Monte Carlo (Metrop-Gibbs) for second Cross-validation
* Step 7: Process second Cross-validation output and check for Convergence
* Step 8: Setup Inputs for Final Cross-validation using Optimal Penalty Terms
* Step 9: Run the Final Model and Visualize the Results

### Final Visualization
If run correctly, the final visual should look something like the image below. This figure shows three plots generated for the Chopper Lake in Alaska. The first visual is the primary Lowess linear fit, the next figure is the resultant lines of our inital seperation by background (regional charcoal influx) and foreground (local charcoal influx) penalty terms with their respective generalized additive model fitting. The final figure is our probability predictions of local fires near Chopper lake for the past 1700 years. The gray shade represents when there is more variation, or less strength, in the models prediction of a probability.
![chopper lake results](https://raw.githubusercontent.com/adraper2/DISC_bayesian/master/AlaskanLakes/chopper_results.png)
