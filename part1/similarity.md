---
# type: page
layout : distill
title:  Data Similarity
author: A.Belcaid
permalink: /similarity/
---

<p align="center">
  <img src="{{ '/part1/data_vis.webp' | relative_url }}" width="480" height="300" alt="Data Mining Image">
  <br>
</p>



## Similarity and Dissimilarity Measures
Data similarity and dissimilarity measures are foundational to numerous data analysis techniques, including clustering, classification, and anomaly detection. In essence, **measuring similarity** (or dissimilarity) between data points allows us to **group**, **classify**, and compare data, which is critical for machine learning, data mining, and even everyday applications like recommendation systems or search engines.

- **Similarity**: This refers to how alike two data points are. Similar items are grouped together in tasks like clustering or nearest neighbor searches. Here are some properties for similarity measure.

  - A numerical measure of a how **alike** data objects are.
  - Is **higher** when objects are  more **alike**.
  - Often falls in the range $[0,1]$.



- **Dissimilarity (Distance)**: This is the opposite how different two data points are. Many machine learning algorithms use distance metrics to quantify this dissimilarity.

  - Numerical measure of how **different** objects are.
  - Lower when objects are more **alike**.
  - Minimum dissimilarity is $0$.
  - **Upper** limit may varies.

The right measure of similarity depends on the type of data and the task at hand. For example, **Euclidean distance** is suitable for continuous numeric data, whereas **Cosine similarity** is preferred for textual data or vectors representing angles.

By understanding how different similarity and distance measures work, we can improve the performance of models and make better data-driven decisions.

----
### simple Attributes
The following table shows the similarity and dissimilarity between two objects, $x$ and $y$, with respect to a single, simple attribute

<center>
<table border="1" cellpadding="10" cellspacing="0">
  <thead style="background-color: #D3D3D3;">
    <tr>
      <th>Attribute Type</th>
      <th>Similarity</th>
      <th>Dissimilarity</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><strong>Nominal</strong></td>
      <td>
        <p>\( s(x, y) = \begin{cases} 1 & \text{if } x = y \\ 0 & \text{if } x \neq y \end{cases} \)</p>
      </td>
      <td>
        <p>\( d(x, y) = \begin{cases} 0 & \text{if } x = y \\ 1 & \text{if } x \neq y \end{cases} \)</p>
      </td>
    </tr>
    <tr>
      <td><strong>Ordinal</strong></td>
      <td>
        <p>\( s(x, y) = 1 - \frac{|r(x) - r(y)|}{n-1} \)</p>
      </td>
      <td>
        <p>\( d(x, y) = \frac{|r(x) - r(y)|}{n-1} \)</p>
      </td>
    </tr>
    <tr>
      <td><strong>Interval/Ratio</strong></td>
      <td>
        <p>\( s= -1, s = \dfrac{1}{1+d}, s = e^{-d}\)</p>
      </td>
      <td>
        <p>\( d(x, y) = \vert x - y\vert \)</p>
      </td>
    </tr>
  </tbody>
</table>
</center>


### Euclidian Distance

Euclidean distance is one of the most widely used distance measures, particularly for continuous numerical data. It is the "ordinary" straight-line distance between two points in Euclidean space. This metric is based on the Pythagorean theorem, and it calculates the distance between two points as the length of the shortest path between them. 

In an $n$-dimensional space, the Euclidean distance between two points $x = (x_1, x_2, \dots, x_n)$ and $ y = (y_1, y_2, \dots, y_n)$ is calculated as follows:


$$
d(x, y) = \sqrt{(x_1 - y_1)^2 + (x_2 - y_2)^2 + \dots + (x_n - y_n)^2}
$$

This formula represents the sum of squared differences between corresponding coordinates of the two points, followed by the square root of the result. Euclidean distance is commonly used in clustering, classification, and other machine learning algorithms.


let's consider the example where we will calculate the Euclidean distances between four points in a 2-dimensional space:

- $ P_1 = (0, 2) $
- $ P_2 = (2, 0) $
- $ P_3 = (3, 1) $
- $ P_4 = (5, 1) $

Each of these points represents coordinates in a 2D space, and we will compute the Euclidean distance between every pair of points to form a distance matrix.

<p align="center">
  <img src="{{ '/part1/points_p1_p2_p3_p4.png' | relative_url }}" width="500" height="480" alt="Data Mining Image">
  <br>
</p>

Here is a summary for the euclidien distances 

<center>
<table border="1" cellpadding="10" cellspacing="0">
  <thead style="background-color: #D3D3D3;">
    <tr>
      <th></th>
      <th>P1</th>
      <th>P2</th>
      <th>P3</th>
      <th>P4</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><strong>P1</strong></td>
      <td>0.000</td>
      <td>2.828</td>
      <td>3.162</td>
      <td>5.099</td>
    </tr>
    <tr>
      <td><strong>P2</strong></td>
      <td>2.828</td>
      <td>0.000</td>
      <td>1.414</td>
      <td>3.162</td>
    </tr>
    <tr>
      <td><strong>P3</strong></td>
      <td>3.162</td>
      <td>1.414</td>
      <td>0.000</td>
      <td>2.000</td>
    </tr>
    <tr>
      <td><strong>P4</strong></td>
      <td>5.099</td>
      <td>3.162</td>
      <td>2.000</td>
      <td>0.000</td>
    </tr>
  </tbody>
</table>
</center>



### Minkowski Distance
### Mahalanobis Distance
### Common properties
### Binary Vectors
### Cosine Similarity
### Correlation
### Information based measures
#### Entropy
#### Mutual Information





