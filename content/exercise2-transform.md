---
layout: default
title: Exercise 2 - Projecting On-the-Fly
nav_order: 10
parent: Exercises
---

## Exercise 2: Projecting on the Fly

*1*{: .circle .circle-blue} From the same project in ArcGIS Pro, click on the the **Canada Lambert** tab representing a different map.

Notice the difference in how the default topographic basemap appears in the previous map compared to this one.

**Reset the data source if you see the red exclamation point.**

Notice the units below the map in the centre.

### *Reflection Question*
(Click the text for the answer)

<details>
<summary>What do these units tell us about the coordinate system this data and map are in?</summary>

<i>When units are in meters, it's a good indication the data is in a projected coordinate system. Data in a geographic coordinate system is usually in decimal degrees.</i>
</details>
<br>

*2*{: .circle .circle-blue} Open the properties of the dataset to see what the coordinate system is.

The **Lambert Conformal Conic Projection** has characteristics which make it a good possible choice for maps of Canada.

- most commonly used projection at Statistics Canada
- retains conformality in mid-latitude regions having primarily an east-west direction
- not equal area because distortion increases north and south of the standard parallel (line at which there is no distortion in the map projection)

*3*{: .circle .circle-blue} Click on the **View** tab at the top of the screen and select **Catalog Pane**. This will open the pane on the right of your map.

*4*{: .circle .circle-blue} Right-click on **Folders** and select **Add Folder Connection**.

![catalogPane.jpg](../images/catalogPane.jpg)

*5*{: .circle .circle-blue} Navigate to the Downloads folder where you downloaded the data for this workshop and click **OK**.

*6*{: .circle .circle-blue} From the **Catalog** pane, expand the **projections-workshop-data>mapProjections>mapProjections.gdb**, and add the **CAN_WGS1984** feature class to the map by dragging it into the **Contents** pane on the left.

Even though you added a feature class which is in a geographic coordinate system, the feature class gets projected "on-the-fly" to match the coordinate system of the map, which in this case is in a projected coordinate system.

ArcGIS Pro chooses a transformation between these two different kinds of coordinate systems that will project the data from one datum to another. You can view the transformations used in the **Map Properties** by right-clicking on the map name under **Drawing Order** in the **Contents** and then clicking on the **Transformation** section.

![transformation.jpg](../images/transformation.jpg)

A **transformation** is a mathematical calculation used to convert coordinates referenced to one datum to coordinates referenced to another datum.

You can see that these two datasets seem to line up perfectly and the units in the lower centre appear as meters.

But projecting on-the-fly does not change the underlying data properties.

*7*{: .circle .circle-blue} Open the properties of the **CAN_WGS1984** to confirm the coordinate system properties.

Taking advantage of on-the-fly projection is okay for visualizing data within the same map.

If you want to do any kind of analysis based on area with your data, you will want to change the projection properties.

We'll go over how to do this in the next exercise.

See additional information on [transformations](https://www.esri.com/arcgis-blog/products/product/mapping/about-geographic-transformations-and-how-to-choose-the-right-one/).
