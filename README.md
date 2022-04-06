# NPZ-Franks
A simple Nutrient-Phytoplankton-Zooplankton ecosystem model

## Introduction

An Nutrient - Phytoplankton - Zooplankton (NPZ) model is used to simulate elemental cycles at the lowest levels of the marine trophic chain. In this case, there are two levels: the phytoplankton and the zooplankton. Phytoplankton, which are the primary producers, are autotrophs - they "produce" their own food - by incorporating elements present in the water in inorganic form (the nutrient pool), such as nitrate (NO3), in a process called nutrient uptake. The zooplankton, which are herbivores, are heterotrophs - they cannot produce their own food - and ingest autotrophs in a process called grazing. Finally, to close the cycle, nutrients in organic matter are returned to an inorganic form (remineralization) and go into the nutrient pool.  

## Model equations

The model equations for the three model compartments N, P and Z are:

(1) dP/dt = (G)rowth - (M)ortality - graz(I)ng,

(2) dZ/dt = (1 - g) * graz(I)ng - mor(T)ality,

(3) dN/dt = -(G)rowth + (M)ortality + mor(T)ality + g * graz(I)ng.

The model currency is N and its total Nt = P + Z + N, is conserved, as (1) + (2) + (3) = 0. 

Nutrient uptake occurs through the growth term G in (1), and the nutrients move to the higher trophic level trough the grazing term I, that appears in (1) as a loss and in (2) as a gain. Phyto and zooplankton mortalities M and T, move nutrients from the two trophic levels to the nutrient pool. In (3) there is an additional term g * I, that represents the amount of unassimilated ingested phytoplankton that goes to the nutrient pool. 

Phytoplankton growth is modeled as a Michaelis-Menten form:

(4) G = (Vm * N)/(Ks + N) * P,

where Vm is the maximum growth rate and Ks is the half-saturation constant. Phytoplankton mortality is a simple linear function:

(5) M = m * P,

where m is the linear loss rate. The grazing term is a Holling Type II form (Ivlev,1955):

(6) I = Rm * (1 - exp(-A * P)) * Z,

where Rm is the maximum ingestion rate and A the rate at which saturation is achieved with increasing food levels.
Zooplankton mortality is also linear:

(7) T = s * Z,

with s the linear loss rate. In (2) and (3), g is the fraction of ingested phytoplankton that is not assimilated.

Ref: Franks, P. J. S., J. S. Wroblewski, and G. R. Flierl. “Behavior of a Simple Plankton Model with Food-Level Acclimation by Herbivores.” Marine Biology 91, no. 1 (April 1986): 121–29. https://doi.org/10.1007/BF00397577.


