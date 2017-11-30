# Shape-from-Silhouettes
3D reconstruction with shape of silhouettes

## Discription
The task is to reconstruct 3D object from multiple calibrated images by implementing a naive silhouette extraction algorithm.
Images and camera calibrations are provided.

### 1. Silhouette extraction
Extract silhouettes from the provided images, using a simple thresholding technique. 
Adjust the silhoutteThreshold so that the silhouettes of the statue are clearly extracted.

### 2. Volume of interest
Define the volume of interest. At first use a larger bounding box than
necessary, just to make sure the statue has included. Then make the bounding box tight to get better resolution.
Similarly, we can start with a coarse grid, say 10 * 10 * 20, and then try a larger grid, at least 64 * 64 * 128.

### 3. Visual hull
Compute the occupancy score at each voxel. For each voxel, transform
the point from volume to world coordinates using the transformation provided. Then
project the points into the image. If a projected point falls within the silhouette, add 1 to
the score.
