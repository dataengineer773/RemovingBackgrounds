We want to isolate the foreground of an image, Mark a rectangle around the desired foreground, then run the GrabCut algorithm, The first thing we notice is that even though GrabCut did a pretty good job, there are still areas of
background left in the image. We could go back and manually mark those areas as background, but in
the real world we have thousands of images and manually fixing them individually is not feasible.
Therefore, we would do well by simply accepting that the image data will still contain some background
noise.
In our solution, we start out by marking a rectangle around the area that contains the foreground.
GrabCut assumes everything outside this rectangle to be background and uses that information to figure
out what is likely background inside the square (to learn how the algorithm does this, check out external
resources like http://bit.ly/2wgbPIS). Then a mask is created that denotes the different definitely/likely
background/foreground regions, The black region is the area outside our rectangle that is assumed to be definitely background. The gray
area is what GrabCut considered likely background, while the white area is likely foreground.
This mask is then used to create a second mask that merges the black and gray regions, The black region is the area outside our rectangle that is assumed to be definitely background. The gray
area is what GrabCut considered likely background, while the white area is likely foreground.
This mask is then used to create a second mask that merges the black and gray regions.
