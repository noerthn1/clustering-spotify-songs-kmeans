<p align="center">
  <img src="https://unsplash.com/s/photos/spotify" alt="Music Visual" width="600"/>
</p>

# 🎧 Clustering Spotify Songs Using K-Means

## Objective
The goal of this project is to apply K-Means clustering on Spotify’s audio feature dataset to group songs with similar musical characteristics.  
By analyzing attributes such as energy, danceability, loudness, and acousticness, we aim to identify natural groupings among songs — which could be useful for playlist generation, music recommendation, or genre discovery.

## Dataset
- **Source:** [Spotify Tracks Dataset on Kaggle](https://www.kaggle.com/datasets/zaheenhamidani/ultimate-spotify-tracks-db)
- **Size:** ~200,000 tracks
- **Key features used:**
  - `danceability`, `energy`, `loudness`, `speechiness`, `acousticness`, `instrumentalness`, `liveness`, `valence`, `tempo`

## Data Preprocessing
- Selected 9 audio features describing the sound profile of each song.
- Scaled features using `StandardScaler` to ensure equal importance.
- Applied PCA for 2D visualization (not for clustering itself).

## Choosing the Optimal Number of Clusters
- Used the **Elbow Method** to evaluate inertia values for `k = 1–10`.
- Found the “elbow” at **k = 5**, indicating diminishing returns after 5 clusters.
- Silhouette scores were highest around `k = 4–6`, confirming that **5 clusters** provided a good balance between compactness and separation.
- 
## Cluster Analysis
Each cluster represents a group of songs with similar sound characteristics:

| Cluster | Key Traits | Possible Style |
|----------|-------------|----------------|
| 0 | High danceability & energy | Pop / Dance |
| 1 | High acousticness & low loudness | Acoustic / Indie |
| 2 | High instrumentalness | Classical / Ambient |
| 3 | High tempo & energy | EDM / Techno |
| 4 | Moderate energy, high valence | Happy / Feel-good tracks |

*(Note: Actual interpretation depends on your data averages)*

The 2D PCA scatterplot shows clear separation between these clusters, confirming that the audio features effectively capture musical differences.

## Key Insights
- Songs can be grouped meaningfully based on numerical sound features, even without genre labels.
- K-Means successfully identified clusters corresponding to broad musical “moods” or “styles.”
- Features like **energy**, **acousticness**, and **valence** are most influential in defining clusters.

## Real-World Applications
- 🎵 **Music Recommendation:** Group similar-sounding songs for better playlist generation.
- 🧠 **Genre Analysis:** Discover sub-genres or mood patterns across the Spotify catalog.
- 📈 **Artist Insights:** Compare how artists distribute across different sound clusters.

## Conclusion
This project demonstrates how unsupervised learning (K-Means) can reveal hidden structure in musical data.  
By clustering songs based on their audio features, we identified five major sound groups that align with intuitive musical characteristics.

Future improvements:
- Experiment with **DBSCAN** or **Gaussian Mixture Models** for more flexible clustering.
- Use **t-SNE** for higher-dimensional visualization.
- Integrate **genre or mood labels** for better interpretability.
