### NumPy Arrays: Shape, Data Type, Indexing and Slicing

I converted the views, likes, dislikes and comment_count columns from the combined DataFrame into NumPy arrays using `to_numpy()`.

I checked the shape and data type of each array to understand the number of records and the type of values stored.

I used `np.sort()` and slicing to identify the 10 largest view counts. I used `views[::100]` to select every 100th record and `views[10:20]` to extract a sub-array containing 10 elements.

These operations helped me understand NumPy array indexing, slicing and data selection.

### Weighted Engagement Score

I calculated a weighted engagement score using three factors: like ratio (50%), normalized views (30%), and normalized comments (20%).

Like ratio receives the highest weight because it indicates positive audience response. Views measure video popularity, while comments represent audience interaction.

The formula is:

Engagement Score = (0.5 × Like Ratio) + (0.3 × Normalized Views) + (0.2 × Normalized Comments)

The resulting score helps compare video engagement using a common scale from 0 to 1. The selected weights represent the assumptions used in this project.