Custom Search JSON/Atom API lets you have up to 100 search queries per day for free, and up 100 pages of search of the same query.

Some of the queries that were the more successful in obtaining images that could easily be applyed to the mesh deformation are:

- Nebula
- Pablo Picasso paintings
- Terrain NASA
- Van Gogh paintings

Most of the images that were were looking for were photographic still pictures with a lot of change of light and colors.
Some of the searches needed different parameters in the URL path query to have a decent image output file. 

Once having obtained a decent amount of images, the images were applyed to a mesh that was calculated earlier. The triangulated mesh is actualy a set of points that are processed into a 2d mesh but with no color. In the following code color is applyed to each triangle of the mesh. The function `surfaceColor.getColorPixel(ci::Vec2i)` throws the color of the pixel in that current position.

```c
for(auto it = vAllDelaunayTri.begin(); it != vAllDelaunayTri.end(); ++it){
	Triangle2* t(*it);
	Point2 * p1 = t->getCorner(0);
	Point2 * p2 = t->getCorner(1);
	Point2 * p3 = t->getCorner(2);

	ci::Vec2i center = ci::Vec2i((int)p1->x(), (int)p1->y())/3.0f + 
			   ci::Vec2i((int)p2->x(), (int)p2->y())/3.0f +
			   ci::Vec2i((int)p3->x(), (int)p3->y())/3.0f;

	ci::ColorA col = surfaceColor.getColorPixel(center);

	mMesh.appendVertex( ci::Vec2f(p1->x(), p1->y()) );
	mMesh.appendColorRgba(col);

	mMesh.appendVertex( ci::Vec2f(p2->x(), p2->y()) );
	mMesh.appendColorRgba(col);

	mMesh.appendVertex( ci::Vec2f(p3->x(), p3->y()));
	mMesh.appendColorRgba(col);

	mMesh.appendTriangle( mMesh.getVertices().size()-3, mMesh.getVertices().size()-2, mMesh.getVertices().size()-1 );
}
```

![Example Image](../project_images/center.png "Particles")

![Example Image](../project_images/twins.png "Particles")


![Example Image](../project_images/six_m.png "Particles")


