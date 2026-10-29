---
title: Mixing probabilities
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

In particular, I view a stratified and turbulent flow as a collection of ‘small’ entities (Lagrangian fluid parcels, also called 'lamellae' here) carrying a given density level and momentum. These fluid parcels are energised by turbulent kinetic energy; in other words, turbulence acts as a ‘thermostat’. Reformulated in this way, a density field stirred and mixed by turbulence is just an out-of-equilibrium large assembly of smaller constituents to which I applied the tools of non-equilibrium statistical mechanics. Let's dig into more of the details now. 

![Stratified flow as a collection of lamellae](/Images/Mixing/figure_lamellar_vision.png)
