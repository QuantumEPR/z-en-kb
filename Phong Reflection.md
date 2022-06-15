# Phong Reflection

A simple model that approximates real reflections.

Take the angle between reflected direction $\mathbf{R}$ and the viewing direction $\mathbf{V}$ to be $\phi$. 

Taking the cosine of $\phi$ causes the brightness to fall off slowly as the viewing angle detracts from the reflected direction.

$$
I_V=I_L\cos{\phi}=I_L \mathbf{V}\cdot\mathbf{R}
$$

In order to get a sharper highlight we can raise the dot product to a power.

$$
I_V=\max\{0,I_L(\mathbf{V}\cdot\mathbf{R})^{\alpha}\}
$$

We also clamp the minimum to be zero as light cannot be negative.
