# ML-EmotionBasedRecommendationSystem 

This project detects emotions from a video of a user using OpenCV and predicts songs from Spotify corresponding to the user's mood from the emotions detected.

First, the project clusters the user's liked songs into 6 playlists corresponding to 6 emotions: **fear, happy, angry, surprised, sad, and neutral**. This is done by using the **Spotify Dataset 1921–2020** found on Kaggle and the **K-Means Clustering Algorithm**. The K-Means Clustering Algorithm is an unsupervised learning algorithm that groups similar data points into **k** groups by calculating distances to centroids. In this project, **k** is set to 6.

[Cluster 0](https://open.spotify.com/playlist/6yvDfcDh1my9pIXWGYLq2k?si=be35a1842c3b40e0) has high values of danceability and low values of speechiness and valence and could correspond to songs one might listen to when feeling fear and wants to divert their mind with high tempo song.

[Cluster 1](https://open.spotify.com/playlist/2WXT06lbhbWWvaJJ7WGAlK?si=aa483296d94b469c) has a low value of valence which correponds to negative emotions in the song and low values of liveliness and danceability as well. Thus it represents songs one might listen to when in a sad mood.

[Cluster 2](https://open.spotify.com/playlist/0lrgUJi282zwjJkN5KGFVq?si=49454821c8f84944) has high values of energy and liveness but low value of valence thus it can correspond to songs one might listen to when in an angry mood.

[Cluster 3](https://open.spotify.com/playlist/5am2EI25FgGFZ514PEQf6b?si=35e500a4d1464adf) has high danceability, liveliness and energy values. It also has a high valence value which depicts a positive uplifiting song. This cluster corresponds to songs one can listen to when happy.

[Cluster 4](https://open.spotify.com/playlist/6CCV3TdQxbxriDQ4qr8Fcd?si=833c4f84b72b42ac) has unusually high loudness and median values for other features. It can include songs one might want to listen to when they wish to be surprised or dont know what to listen to.

[Cluster 5](https://open.spotify.com/playlist/1XGeqvSdPF8MZmj6VyZby8?si=9d1f996edd874208) has high values of instrumentalness and low values of speechiness and danceability, this can correpond to neutral emotions.


Next, the project develops a detector to determine the mood of the user from a video of their face. This is done using the **Face Emotion Recognizer (FER) library**. The FER library uses a **convolution neural network** to classify emotions into 6 categories: **fear, neutral, happy, sad, anger, and disgust**. The FER library has an accuracy of **98%** on the **FER2013 dataset**.


Finally, the project combines the two parts to create a system that can detect the user's mood and recommend songs from Spotify that match the user's mood.

Here is an example of the project's output for a classic Michael Scott gif:

![happy-emotional](https://user-images.githubusercontent.com/96650742/186596589-b178e2c8-dfe7-4b11-a363-3648be831352.gif) ![Graph](https://user-images.githubusercontent.com/96650742/186598719-3614eb21-cf2a-4c9c-8de0-7d1d5fd5d6c2.png)

Once I had obtained the emotion of the user and detected their mood I now simply had to use the Spotify API to suggest songs from the playlist I had already created corresponding to the respective mood. Here's what the model came up with for the above gif:

![Recommendations](https://user-images.githubusercontent.com/96650742/186599065-ed47a82a-2ce0-417c-819b-bac67df794d9.png)

You can find the results for a couple more samples in the results folder. I had a great experience making this project wherein I got to learn about the real time applications of CV and the working of a recommendation system in detail and would love to build on similar such ideas in the future.


The gif shows Michael Scott from The Office smiling and laughing. The FER library detects the emotion in the gif as **happy**, with a confidence of **0.98**. The project then recommends songs from Spotify that are classified as **happy**.


The project is still under development, but it has the potential to be a useful tool for people who want to find songs that match their mood.

Here are some of the challenges that the project faced:

* The FER library is not always accurate. Sometimes, the library will incorrectly classify the emotion in a video.
* The project can be computationally expensive. The K-Means Clustering Algorithm and the FER library both require a lot of computation.

Here are some of the next steps for the project:

* Improve the accuracy of the FER library.
* Make the project more computationally efficient.
* Add more features to the project, such as the ability to recommend songs from other streaming services.

Overall, this project is a promising step towards the development of a more personalized music recommendation system.

Possible improvements possible in this project could be deploying this model as a web-app that can take real time video data as input and allow the user to sign in to their spotify account and classify and recommend music from their liked songs based on the mood detected.

