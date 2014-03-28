## Particles and Triangulation

The antecedent of the project Manifold, comes form a prototype project named Aether.

To create the visual I'm going to explain how the magic is done.

First I create a dynamic particle system in cinder. The particle system has simple interaction forces like repulsion and attraction.

In the following image all the particles are have a attraction force to the center of the canvas. But also all the particle have a small repulsion force. This to have the collision between each of the particle work.

![Example Image](../project_images/particles01.png "Particles")

Without the attracting force to the center. A mesh of points

![Example Image](../project_images/particles-noCenter.png "Mesh")

Once having a real time particle system that has interaction forces like repulsion and attraction the next step is feed the points to a Delaunay triangulation algorithm. The triangulation that i'm using can execute the Delaunay triangulation in real time.

![Example Image](../project_images/manifold-triangulation.png "Triangulation")

![Example Image](../project_images/mesh.png "Triangulation")

The final output is a mesh of points draw on a canvas. The canvas includes calculating the Delaunay triangulation of a set of points that behave on a physics simulation.

The idea is to provide the colors of the particles and the triangulated mesh with images taken from the web. This still images come to life with the hand movement of the participants. With the interaction of the users they are able to alter the different viewpoints of the images.

The next step is to feed the 2D mesh with various Textures. The source of the textures are going to be obtain using the Custom Search API from google.
