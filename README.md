# 🏙️ City Clustering using K-means Clustering on Night Satellite Images

This project uses satellite images of night-time city clusters to group illuminated areas into distinct clusters. It implements the K-means clustering algorithm from scratch in a Jupyter Notebook to segment the cities based on the brightness patterns in the images.

## 📂 Repository Structure
├── 1.png<br>
├── 2.png<br>
├── 3.png<br>
├── 4.png<br>
└── city_clustering.ipynb

- **🖼️ Images:** The folder contains four satellite images (`1.png`, `2.png`, `3.png`, and `4.png`) representing different city clusters.
- **📓 Notebook:** `city_clustering.ipynb` includes the full code for preprocessing the images, running the clustering algorithm, and visualizing the results.

## 🔍 Project Overview

- **🖌️ Image Preprocessing:**  
  The code loads each image using Pillow, converts it into a NumPy array, and then extracts the grayscale version by taking a single channel (since the satellite images are processed by their brightness).

- **🧩 Clustering with K-means:**  
  The K-means algorithm is implemented from scratch. The process includes:
  - **⚙️ Initialization:** Randomly selecting `k` initial centroids from the set of non-zero (bright) pixels.
  - **🎯 Assignment:** Grouping each pixel with the nearest centroid based on Euclidean distance.
  - **🔄 Update:** Recalculating the centroids as the mean of the points in each cluster.
  - **✅ Convergence Check:** The algorithm stops when centroids move less than a specified tolerance between iterations.

- **📈 Elbow Method:**  
  An elbow method is used to calculate the Within-Cluster Sum of Squares (WCSS) for different values of `k`. This helps in determining the optimal number of clusters for each image:
  - **Image 1:** Optimal clusters = 3
  - **Image 2:** Optimal clusters = 3
  - **Image 3:** Optimal clusters = 4
  - **Image 4:** Optimal clusters = 2

- **📊 Visualization:**  
  Clusters are plotted with distinct colors. Centroids are highlighted, and pairwise distances between centroids are computed and displayed in a table format.

## 📦 Dependencies

Make sure you have Python 3.x installed. The project depends on the following packages:

- [Pillow](https://python-pillow.org/) (for image processing) 🖼️
- [NumPy](https://numpy.org/) (for numerical computations) 🔢
- [Matplotlib](https://matplotlib.org/) (for plotting) 📉
- Jupyter Notebook 📓

Install the required packages using pip:
    ```bash
    pip install pillow numpy matplotlib
    ```

# 🚀 **How to Run the Project**  
----------------------
1. **🔗 Clone the Repository:**
   
    ```bash
    git clone https://github.com/your-username/your-repository.git
    ```

2. **📁 Navigate to the Project Directory:**
   
   ```bash
   cd your-repository
   ```

3. **💻 Launch the Jupyter Notebook:**
   
   ```bash
   jupyter notebook city_clustering.ipynb
   ```

4. **▶️ Run the Notebook Cells:**  
   Execute the cells sequentially to perform clustering on each image and view the corresponding visualizations.

-------------------------

📝 **Code Breakdown**  
---------------------

* **🖼️ Image Loading & Preprocessing:**  
  The notebook loads each satellite image and extracts its grayscale representation by selecting one of the color channels. It then identifies the light points (pixels with values greater than 0) for clustering.
    
* **🧮 K-means Clustering:**  
  The `k_means_clustering` function implements the clustering algorithm:
    
  * **⚙️ Initialization:** Random centroids are chosen from the available light points.
  * **🎯 Assignment:** Each point is assigned to the nearest centroid.
  * **🔄 Update:** Centroids are updated based on the mean of the assigned points.
  * **✅ Convergence:** The algorithm stops once the centroids stabilize.

* **📈 Elbow Method & Visualization:**  
  The `elbow_method` function computes the WCSS for different values of `k` to help decide the optimal number of clusters. The `cluster_plot` and `distance` functions then plot the clusters along with centroid markers and display the distances between them.






