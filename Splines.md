# Splines

## Motivation

How do we specify curves?

Imagine using a wire/wood strip and we pin it down using weights on specific points.

This is the same as to solve for a smooth interpolating curve passing through each control point.

For each point $f(t)$ on the curve, consider $f(t-1),f(t),f(t+1)$ with the following:

$$
\min (f(t-1)-2f(t)+f(t+1))^2
$$

which is an approximation of minizing energy at each point. As we take more and more samples, at infinity we get the natural cubic spline.

Of course, we don't need to use such method to solve for splines. Consider a cubic

$$
at^3+bt^2+ct+d
$$

Here, $d$ controlls a constant offset, $c$ controlls the orientation, $b$ controlls the curvature, and $a$ adds another wiggle.

To solve for a interpolating polynomial we can plug in the control points and solve the linear system.

$$
\begin{bmatrix}
t_1^3 & t_1^2 & t_1 & 1\\
t_2^3 & t_2^2 & t_2 & 1\\
t_3^3 & t_3^2 & t_3 & 1\\
t_4^3 & t_4^2 & t_4 & 1
\end{bmatrix}
\begin{bmatrix}
a\\b\\c\\d
\end{bmatrix}=
\begin{bmatrix}
c_1\\c_2\\c_3\\c_4
\end{bmatrix}
$$
Another way is to use control points with their first derivatives.

$$
\begin{bmatrix}
t_1^3 & t_1^2 & t_1 & 1\\
t_2^3 & t_2^2 & t_2 & 1\\
3t_1^2 & t_1 & t_1 & 0\\
3t_2^2 & t_2 & t_2 & 0
\end{bmatrix}
\begin{bmatrix}
a\\b\\c\\d
\end{bmatrix}=
\begin{bmatrix}
c_1\\c_2\\d_1\\d_2
\end{bmatrix}
$$

To fit more control points, rather than using higher order polynomials, we fit a cubic spline for each pairwise contiguous points. To avoid knots we also restrict the tangent to be equal for the same point between the splines. Such is called the a $C_1$ continuity. 

We can set the tangent equal to the secant line from the previous control point to the next. This kind is called a Catmull-Rom spline. This is equivalent to sliding a cubic filter to interpolate a sequence of points.

Remember that to fit a curve of three points, we will have 2 pairs and thus 4 equations. With the equal first derivative constraint we will have a total of 5 equations.

If we set the second derivative to be equal, we will have 6 equations. We will also set the second derivative at the start and the end point to be 0. In conclusion we will have 8 equations.

We will see that Catmull-Rom has local control while Natural Cubic does not.

There exists a caveat of specifying a pair of control points with their derivatives. When their interval is between 0 and 1 the tangent gets very long.