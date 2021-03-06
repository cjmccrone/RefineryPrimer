# Building Mass Generator

<p align="center">
  <img src="../../assets/sample/workflow11.gif" style="width:200px;"/>
</p>

## Description

This graph, used with the _`Randomize`_ mode, will generate a series of random towers, sitting across a stipulated site boundary. 

The tower will randomize heights, floor plate designs and orientations, allowing for a large number of potential design solutions within minutes.

We will work with the Randomize method because in this example we are interested in navigating through a variety of building shapes rather than optimizing an evaluator. Some of the variables used in this workflow are intended to create variation rather than optimization, so using this method is more appropriate.

[Download workflow files](https://github.com/DynamoDS/RefineryPrimer/releases/download/samples-v2/04-02-01_Building-mass-generator.zip).

## Static Inputs

| Name | Description |
| :--- | :--- |
| Site boundary | Select the site boundary lines from the Revit model \(model curves\) |

## Variable Inputs

| Name | Description |
| :--- | :--- |
| Site offset \(mm\) | A number to define the offset from the site boundary |
| Building height \(mm\) | Range for the total height of the tower |
| Floor height \(mm\) | Range for the floor-to-floor height of the tower |
| U Values \(%\) | U Parameters at surface for the seven points that will create the base floor plate |
| V Values \(%\) | V Parameters at surface for the seven points that will create the base floor plate |

## Functions

The script is made up of a series of functions, which are divided into groups inside the graph. Each group has a name and a short description, where the name indicates the type of function being run and the description explains in more detail the process.

The graph takes the site boundary from Revit, the offset, and the U and V values from the user inputs and generates the base floor plate for the new tower inside the allowed space. Using the building height and the floor-to-floor height, the script then generates all the other floors based on the initial floor plate with slight variations. Once all the floor plates are created, the script creates the external walls by lofting the outer floor boundaries.

With the geometry of the building generated, the script then evaluates the design based on the outputs defined.

## Evaluators

| Name | Description |
| :--- | :--- |
| Public realm area \(m2\) | The total area available at ground floor that sits outside of the floor plate but inside the site boundary |
| Total building area \(m2\) | The total area of the entire building |
| Lift provision area \(m2\) | The total area of the lifts required for the building |

## Visualization

When geometry is created in Dynamo, often other geometry is needed to facilitate the overall process. 

Please note that all unnecessary geometry has been switched off in Dynamo - this is to ensure the geometry displayed shows the final geometric output. Any nodes with the preview switched off will not display the output visually in Explore Outcomes.

In this case, only the site boundary \(the tower's external walls and floors\) will be visible. This will provide the user with the ability to critique the design options based on aesthetics within the thumbnail or detail view. 

A series of context buildings have been included in the Revit sample file for a better understanding of the exercise.

## Benefit of Using Generative Design

When running the script in Dynamo, a single design option is generated for each run, based on the current user inputs. However, by running the script in Generative Design for Revit and selecting Randomize as the generation method, many more options can be generated at the same time. 

Due to the nature of this graph, it works best when using the 'Randomize' mode. Although the outputs can be used to maximize or minimize the various areas, the optimization approach won't work as there is no pattern for the algorithm to use. By using the 'Randomize' mode, Generative Design can produce hundreds - if not thousands - of different iterations, allowing the user to rank and explore the options to find the best option.

## Results

Once running the study type is finished, the outcomes can be explored through the tables and graphs available. 

The image below shows an example output from a randomized study based on 40 solutions.

<p align="center">
<img src="../../assets/sample/workflow12.png" style="width:85%;"/>
</p>

## Video Tutorial

{% embed url="https://www.youtube.com/watch?v=FVnKMHEXmaQ" %}

{% page-ref page="./" %}
