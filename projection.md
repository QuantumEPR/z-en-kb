# Projection

A screen would not work without a Pin-hole camera.

Size of aperture effects both the brightness and blur of the image.

A lens can refocus the light via refraction.

We need to place the image plane where the rays converge.

A wide aperture results in a narrow depth of field, which means only the narrow part around the focal point (and the focal point) is clear.

## Perspective projection

Object get scaled by $1/z$.

The center of lens is called the center of projection.

Steps to do perspective projection:
$$
\begin{bmatrix}1&0&0&0\\0&1&0&0\\0&0&1&0\end{bmatrix}\begin{bmatrix}x\\ y\\ z\\ 1\end{bmatrix}=\begin{bmatrix}x\\y\\z\end{bmatrix}\rightarrow\begin{bmatrix}x/z\\y/z\end{bmatrix}
$$

In general,
$$
SPTRv
$$

Scaling the distance of the screen to the center of projection magnifies the image by the same factor and reduces the field of view by the inverse of the same factor.