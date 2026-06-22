# Polygon Area Splitter

This file includes various functions needed to split a polygon in half with respect to area.

All polygons are represented as a list of vertices in clockwise or counterclockwise order. If two vertices are next to one another in the list, they have an edge connecting them. 

## Functions Included:

* **area**
  * Uses Shoelace Theorem to find area.
  * **Input:** Vertices of polygon.
  * **Returns:** The area of the polygon.

* **area_below_c**
  * Calculates the area of the polygon below the line defined by $w^Tx=c$.
  * **Input:** Vertices of a polygon, the normal vector $w$ to the direction of cutting, and the displacement $c$ from the origin of the cutting line.
  * **Returns:** Area of the polygon below the line, the sub-polygon defined below the cut, and the vertices exactly along the cut line.

* **find_half**
  * Iterates to find the displacement from the origin that splits the polygon exactly in half with respect to area. Works for both convex and non-convex polygons.
  * **Input:** Vertices of a polygon, the normal vector $w$ to the direction of cutting, an $\epsilon > 0$ that determines the degree of accuracy of the line found, and (optional, default 100) the maximum number of iterations.
  * **Returns:** The subshape defined by the polygon below the line, and $c$ (the displacement from the origin of the cutting line).

* **point_on_edge_at_c**
  * Given a particular edge of the polygon (defined by the vertices at each end), finds the intersection point of the cutting line with the edge.
  * **Input:** Vertices of the polygon, direction normal to the direction of cut ($w$), index of the first vertex in the edge (first based on direction of polygon, i.e. counterclockwise or clockwise), displacement from the origin ($c$).

* **exact_half**
  * Looks only at the vertices of the polygon before defining a subrange of possible values of $c$ (displacement) and then solving directly for the exact value of $c$ using the Quadratic Formula (must exist because of IVT). Works for both convex polygons and non-convex polygons!!
  * **Input:** Vertices of the polygon and the direction normal to the direction of cutting ($w$).
  * **Returns:** The subshape defined by the polygon below the line, and $c$ (the displacement from the origin of the cutting line).

* **ploting**
  * Creates a plot of the original polygon, the cutting line, and the area below the cutting line.
  * **Input:** The vertices of the polygon, the direction normal to the direction of cutting ($w$), and the displacement from the origin of the cutting line ($c$).
  * **Returns:** Nothing.

* **find_half_trace**
  * Creates an animation that shows the movement of the cutting line and value of $c$ across iterations of the find_half function.
  * **Input:** Vertices of the polygon, the direction normal to the direction of cutting ($w$), $\epsilon > 0$ which defines the accuracy of the solver, and (optional, default=100) the maximum number of iterations of the solver.
  * **Output:** Nothing.

## Examples
Examples and animated outputs can be found at the bottom of the notebook.
