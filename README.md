# PhD-Proposal-Files
Model desecription of project 2b

We propose a model of cultural evolution in which cultural traits, hereafter referred to as "tools," occur in specialized and in non-specialized populations. 
The degree of population specialization is defined as the number of guilds into which it is divided. 
Non-specialized populations, hence, are considered as consisting of one guild. 
The cultural dynamics within each guild are completely independent from other guilds, meaning there are no shared tools between them.

Our model is roughly based on the modeling framework of Kolodny et al. 2015 for independent cultural innovations, termed main axis tools in the original model, with adjustments for the division into guilds. 
In the model presented here, new tools are invented at a given rate per individual per time-unit, which was set at 0.001, similarly to the original model. 
This means the number of invented tools per time-unit is linearly dependent on population size (regardless of division to guilds). 
Realistically, the relation can exceed linear (as demonstrated in Kolodny et al. 2015) because existing tools can be used to invent new tools, but for simplicity, our version of the model assumes the inventions of tools are independent from one another.

Invented tools can be lost in two ways. 
First, newly invented tools can be lost before being established in the population. 
Each new tool is associated with a positive selection coefficient s, which is drawn from an exponential distribution with parameter β = 0.01. 
We do not explicitly simulate the cultural transmission process that would result in this type of loss; instead, as in Kolodny et al. 2015, we use an approximation that a newly invented tool is stochastically lost with probability 1−s. Thus, with probability s, a newly invented tool is established and is immediately considered to have reached its equilibrium frequency in the population.

In addition, after a tool has been established in the population, it can still be lost due to drift. Kolodny et al. did not attend to the issue of specialization, and therefore did not consider each individual’s potential capacity to accumulate cultural traits or the level of overlap between individual repertoires. 
Hence, in the original model, the probability of loss of an individual tool was in negative linear relation to the population size.

In our model, we consider that the repertoire size may also be limited by each individual’s capacity to accumulate cultural traits. 
We thus assume that the probability of loss of a tool is also exponentially dependent on the existing repertoire size. 
That is, the bigger the cultural repertoire, the harder it becomes to remember all tools and transmit them to the next generation. 
The loss function we used is (1.001^population repertoire size)/(500*population size).

We also examined alternative approaches to simulate the relation between the existing repertoire and the probability of loss, which yielded similar results. 
One such example (demonstrated in Figure S1) was to assume that probability of loss of tools is independent of repertoire size (as in Kolodny et. al 2015), but that there is a maximal repertoire that a guild can achieve, which is derived from the individual capacity for knowledge. 
This follows from the assumption that within a guild, most individuals know most tools, so the total repertoire of a guild cannot greatly exceed what one person can learn individually.

In our simulations, the cultural repertoire size of a population plateaus, reaching a steady state at which the number of tools fluctuates stochastically around a stable value. 
The repertoire size of a population at this steady state, termed here as average cultural repertoire size, was estimated by averaging the observed repertoire of a population between time steps 200,000 (at which it has already plateaued) and 500,000. 
In cases when we measured the average cultural repertoire at different time points in a simulation, such as before and after a bottleneck, we similarly averaged over 300,000 time steps after the repertoire size had plateaued.

First, we examine the relationship between population size and repertoire size in non-specialized populations; then, we examine the average cultural repertoire sizes achieved by different numbers of guilds for different population sizes. 
Increasing the level of specialization can potentially allow a population to maintain a larger cultural repertoire, but subdividing into too many guilds might lead to increased cultural losses as the number of individuals in each guild decreases. 
The number of guilds that leads to the largest average cultural repertoire size of a population is termed the repertoire-maximizing number of guilds.

Assuming a guild that loses a high percentage of its repertoire within a short time frame may collapse, highly specialized populations composed of many small guilds may not be sustainable. Thus, we compare repertoire-size stochasticity for guilds of different sizes.

Finally, we demonstrate how demographic and environmental changes might affect repertoire size differently in non-specialized and specialized populations. In all analyses in this section, we start by allowing both populations to reach a steady-state repertoire size. 
In the first analysis, we then let population size fluctuate: with a default probability of 0.00001 per time step, the population can increase or decrease by 200 individuals, with the total population size constrained to between 600 and 1000 individuals. 
In the second analysis, we impose a fluctuating environment. 
We define a probability of 0.0001 for shift between two environments, assuming that 90% of tools invented in a given environment are only useful in that environment, which results in a 10-fold increase in their probability of loss in the alternative environment.
