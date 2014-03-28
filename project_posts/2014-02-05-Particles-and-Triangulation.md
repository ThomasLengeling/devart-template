## Particles and Triangulation

The antecedent of the project Manifold, comes form a prototype project named Aether.

First we are going to develop a dynamic particle system in Cinder. The particle system has simple interaction forces like repulsion and attraction. But also the particle are rendered in real time for continuous interaction with the user and the sound. Because we need the particle system to be rendered in real time, we are going to use Euler Integration to solve the particles positions. Euler's Integration is the fastest method for solving particles positions but not as numerical precise as the Runge Kutta method.

We start programming a particle system similar to Memo Akten's MSAPhysics and Daniel Shiffman Particle System. 

Some results after developing the system.
In the following image all the particles have an attraction force to the center. But, also, all the particle have a small repulsion force. This is to have the collision between each of the particle work.

![Example Image](../project_images/particles01.png "Particles")

Without the attracting force to the center. A mesh of points

![Example Image](../project_images/particles-noCenter.png "Mesh")

Once having a real time particle system that has interaction forces like repulsion and attraction, the next step is to feed the points to a Delaunay triangulation algorithm.

We tryed many Delaunay triangulations that are available in the web like polyTri, s-hull, built in cinder triangulation and triangle. The one that worked best for us was [triangle](http://www.cs.cmu.edu/~quake/triangle.html).
The triangulation that we used can execute the Delaunay triangulation of more than 3000 points in real time.

![Example Image](../project_images/manifold-triangulation.png "Triangulation")

![Example Image](../project_images/mesh.png "Triangulation")

The final output is a mesh of points drawn on a canvas. The canvas includes calculating the Delaunay triangulation of a set of points that behave in accordance with the physics simulation.

The idea is to use the Custom Search API from Google to obtain as many images as possible and feed these images to the triangulated mesh. The images will only provide the color for each triangle of the mesh. These still images come to life with the hand movement of the participants.

The next step is to feed the 2D mesh with various textures. The source of the textures is going to be obtained using the Custom Search API from Google.
