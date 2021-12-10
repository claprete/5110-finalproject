# 5110-finalproject
Math Bio 5110 final project for Carolyn LaPrete, Avery Hazelbaker, Sage Acord

We wrote all of the code in one .mlx notebook file that must be downloaded to view and generate figures. Run the first section to generate figures from 1e, and the second section for 1f. The end of the first section includes the inputs for plotting the phase plane in pplane.jar, see below for more details.

### Function at the end of the file used for both sections:
G is the Goldbeter-Koshland function defined in the paper and used in both dR/dt equations.

### The first section is for 1e
##### To generate an R-t plot of the system of differential equations for R and X:
We store all given parameters and set the endtime to 40. <br />
Ep is set to be the G function at R, so G is called with the current R passed into Ep at each time for the solver. <br />
Define the system of equations as a vector dRdt with inputs t and v, where v is vector [R;X].<br />
For each of the initial values of X (X_i = 20,40,100), we
 - set the intial value of v to [0;X_i]
 - solve for t and V using ode23s from time 0 to endtime
 - plot the first column of V (the R values) vs. time

To generate an R-X phase plane, we use pplane.jar with inputs explained in the file, where each header corresponds to a section of inputs in the pplane window. We then graph and select Solution>Show Nullclines and Options>Solution Direction>Forward, then click places on the plane to plot solutions there.


### The second section is for 1f
##### To generate a dR/dt-R plot of the function dR/dt:
We store all given parameters and set the endR to 1.5, also generating Rspan from 0 to endR. <br />
Ep is set to be the G function at R, so G is called with the current R passed into Ep at each time for the solver. <br />
We then generate a function dRdt_prod that is the production of the response component and a function dRdt_rem that is the removal fo the response component. <br />
dRdt_prod is plotted over Rspan. <br />
We set the parameter S to 0.6 and plot dRdt_rem over Rspan. We repeat this for S = 1.2 and 1.8.
