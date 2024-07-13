# Monte Carlo Liquid Crystal

## How it works

I want to simulate a nematic/smectic liquid crystal under the action of a magnetic field. Therefore,

* It is 2D.
* Molecules will be placed on a grid. Can I still consider it a nematic?
* I only keep track of orientations of the molecules.
* Rod shaped
* I will generate at each iteration a new grid and only keep it if it minimizes energy E.


Two terms will account for the density energy $j$. The first is related to the magnetic field of intensity B. Since molecules will try to align with the field, we give it the form,

$$j_\text{mag} = B^2 \cos^2(\phi)$$


The next term contributing to density is a coupling term. We compute the average orientation $\phi_\text{avg}$ of neighbors and proceed to compute the following density,

$$j_\text{neigh} = - K \cos^2(\phi - \phi_\text{avg})$$

As molecules want to align with neighbors. K is just a coupling constant. Finally, computing E is done by summing all densities,

$$ E = \sum_{\alpha,\beta} j_{\alpha,\beta}$$
