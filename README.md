# Shape-from-Silhouettes
3D reconstruction with shape of silhouettes

## Discription
The task is to reconstruct 3D object from multiple calibrated images by implementing a naive silhouette extraction algorithm.
Images and camera calibrations are provided.

### 1. Silhouette extraction
Extract silhouettes from the provided images, using a simple thresholding technique. 
Adjust the silhoutteThreshold so that the silhouettes of the statue are clearly extracted.

![image](https://user-images.githubusercontent.com/29389892/35713540-296a6336-07c8-11e8-8c35-4a137b701128.png)

### 2. Volume of interest
Define the volume of interest. At first use a larger bounding box than
necessary, just to make sure the statue has been included. Then make the bounding box tight to get better resolution.
Similarly, we can start with a coarse grid, say 10 * 10 * 20, and then try a larger grid, at least 64 * 64 * 128.

<img src="https://user-images.githubusercontent.com/29389892/35713570-550f7c24-07c8-11e8-8ac1-bc7a0598b8c5.png" width="370" height="280">

### 3. Visual hull
Compute the occupancy score at each voxel. For each voxel, transform
the point from volume to world coordinates using the transformation provided. Then
project the points into the image. If a projected point falls within the silhouette, add 1 to
the score.

<img src="https://user-images.githubusercontent.com/29389892/35713772-77b0a2d4-07c9-11e8-8a85-621e10f04f9b.png" width="270" height="500">
