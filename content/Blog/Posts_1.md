---
title: Mixing probabilities
date: '2026-10-28'
blog:
  - Mixing probabilities
---

Mixing describes the **irreversible** time-evolution of a scalar field from a partitioned state to a fully homogeneous one, as it is stirred by some velocity field. Here, the scalar field we consider is density, and the stirring velocity is some flavour of turbulence. 

![Stirring, mixing](/Images/Mixing/figure_description_stirring_mixing.jpg)
*Stirring and mixing a box filled with two densities `$\rho_{1}$` and `$\rho_{2}$`.*

As the scalar field is mixed, the probability of finding a density `$\rho$` in the box (denoted `$p(\rho)$`) evolves. In the case depicted above, we have initially `$p(\rho) = \delta(\rho - \rho_{1}) + \delta(\rho - \rho_{2})$`. Here `$\delta$` is the Dirac distribution. As time evolve
`$$p(\rho) \xrightarrow[t \to +\infty]{} \delta(\rho - \langle \rho \rangle), \quad \langle \rho \rangle = \frac{\rho_{1} + \rho_{2}}{2}. $$`

**What is the time-scale `$t_{\ast}$` for this limit to happen?**

Why is `$t_{\ast}$` important? Getting an scaling of `$t_{\ast}$` in terms of measurable, large-scale quantities of the flow can help us infer the large-scale effect of small-scale mixing through an 'eddy-diffusivity' `$D_{\ast}$`, the quantity that ocean and climate models rely on to parameterize unresolved processes. *Add definition of eddy-diffusivity*. Considering a grid cell of size `$H$` in a numerical model, `$t_{\ast}$` is the time for unresolved processes to diffuse any density perturbations away; it is then natural to define `$D_{\ast} = H^{2} / t_{\ast}$`. 

Common parameterisations rely on the fact that mixing might be tied to some kind of overturning process: a Kelvin-Helmotz billow breaks down into turbulence that stirs and eventually mixes density pertubation. There is however no evidence that ocean mixing rely solely on such instabilies. In fact, following that line of though might [miss](/publications/Publications/Applicability_stability_based_paradigm_mixing.pdf) a lot of mixing in the interior. 

Here, we pursue a route that is **agnostic to the small-scale stirring protocols**—wave breaking, billows, or overturns. We argue that the coarse-grained properties of a the density field (described by `$p(\rho)$`) as it is stirred and mixed are somewhat general. This route follows common ideas of **statistical mechanics**. 

In particular, I view a stratified and turbulent flow as a collection of ‘small’ entities (Lagrangian fluid parcels, also called 'lamellae' here) carrying a given density level and momentum. These fluid parcels are energised by turbulent energy; in other words, turbulence acts as a ‘thermostat’. Reformulated in this way, a density field stirred and mixed by turbulence is just an out-of-equilibrium large assembly of smaller constituents (the lamellae) to which I applied the tools of non-equilibrium statistical mechanics. Let's dig into more of the details now. 

![Stratified flow as a collection of lamellae](/Images/Mixing/figure_lamellar_vision.png)
*A density field as a collection of lamellae.* 

In the figure above, we present a density field stirred by turbulence. Red corresponds to a fluid parcel that is denser than a set background density field; blue correspond to a parcel that is less dense than the background. The small-scale elongated structures are what we call 'lamellae'. They carry a given density level: 

- In the absence of mixing (i.e. no molecular diffusivity), the density level carried by a lamella is constant. Statistical mechanics tells us that, in that case, the collective behaviour of the lamellae in contact with the turbulent thermostat organises, after some time, the coarse-grained density field into a stable equilibrium state of [maximum disorder](https://www.cambridge.org/core/journals/journal-of-fluid-mechanics/article/abs/statistical-mechanics-approach-to-mixing-in-stratified-fluids/1F764D637D30C2E6B89852CB226FE041). This can be understood as follows. The turbulent energy wants to disperse the lamellae away from their neutrally buoyant positions. Buoyancy forces want to bring them back. This is the dashed trajectory on the right panel. The competition between these two effects allows for dispersion to be limited (if no buoyancy forces were present, the lamellae will just run away forever, as in classic dispersion) and an [equilibrium state to be reached](/publications/Publications/CTR_Research_brief.pdf). This process can be mathematically be described by the following equation for the probability of finding a density level `$\rho$` at depth `$z$`: 
`$$
    \partial_{t}p = \underbrace{D\partial_{z}^{2}p}_{\textbf{\textcolor{pink}{dispersion}}} + \underbrace{\frac{Dg}{\beta\rho_{0}}\partial_{z}[(\rho-\overline{\rho})p]}_{\textbf{\textcolor{pink}{buoyancy forces}}}, \quad \overline{\rho}(z) = \int\rho p(\rho, z)\mathrm{d}\rho. 
$$`
The particular form is unimportant here; what matters is that the time evolution of `$p$` is controlled by the competition between dispersion (the thermostat) and buoyancy forces. 

- In the presence of mixing, lamellae exhange density: they interact. This interaction term is what allows mixing to bring the density field from its initial state to a fully homogeneous state. The interaction term works as follows: two lamellae with density `$\rho_{1}$` and `$\rho_{1}$` will create a lamella with density `$(\rho_{1} + \rho_2) / 2$` after a *mixing time* `$t_{M}$` (that as been characterised experimentally [here](/publications/Publications/prandtl_number_effects_on_extreme_mixing_events_in_forced_stratified_turbulence.pdf)). Mathematically, that gives
`$$
    \partial_{t}p = \underbrace{D\partial_{z}^{2}p}_{\textbf{\textcolor{pink}{dispersion}}} + \underbrace{\frac{Dg}{\beta\rho_{0}}\partial_{z}[(\rho-\overline{\rho})p]}_{\textbf{\textcolor{pink}{buoyancy forces}}} + \frac{1}{t_{M}}\underbrace{(-p + p_{\alpha} \ast p_{1-\alpha})}_{\textbf{\textcolor{green}{interaction/mixing}}}. 
$$`

The study of a prototypical setup allows to scale all the free parameters of the model in terms of large-scale, measurable properties of the flow. The details are given [here](/publications/Publications/routes_towards_homogeneity_in_stratified_turbulent_flows.pdf). In particular, the analysis of the above equation gives `$t_{\ast}$` in different regimes.  
