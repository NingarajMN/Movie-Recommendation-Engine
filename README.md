Movie Recommendation Engine using GraphRAG
Overview
This project implements a movie recommendation engine using the GraphRAG architecture and Neo4j. The engine recommends similar movies based on the movie a user has watched. For example, if a user watches "3 Idiots", the engine will recommend three similar movies.

Features
Graph Database: Utilizes Neo4j to store and query movie data.
GraphRAG Architecture: Combines knowledge graphs and retrieval-augmented generation for enhanced recommendations.
Interactive Visualization: Visualize the movie graph using Neovis.js.
Dataset
The dataset used in this project is sourced from Kaggle. It contains information about 10,000 Bollywood movies, including titles, genres, actors, directors, and more.

Installation
Prerequisites
Python 3.x
Neo4j (Community Edition)
Neo4j Python Driver
Neovis.js

Usage
Running the Recommendation Engine
Start the Recommendation Engine:

python recommendation_engine.py
Get Recommendations:

The script will prompt you to enter a movie title.
It will then return three similar movie recommendations.
Examples of Usage
Example 1:
Enter the movie title: Dangal
Recommendations: 
1. Sultan
2. Chak De! India
3. Bhaag Milkha Bhaag
Visualization
Open the Visualization:
Open the index.html file in a web browser to visualize the movie graph.
Project Structure
MovieRecommendationEngine/

├── input_database/
│   └── bollywood_dataset.csv
│
├── code/
│   ├── load_data.py
│   └── recommendation_engine.py
│
├── model_architecture/
│   └── architecture_slide.pptx
│
├── demo_video/
│   └── demo.mp4
│
└── index.html
Model Architecture
The recommendation engine uses the GraphRAG architecture, which combines knowledge graphs and retrieval-augmented generation. The architecture leverages Neo4j for storing and querying movie data and uses a Python script to generate recommendations.


Example Evaluation
from sklearn.metrics import precision_score, recall_score, f1_score

# Example data
true_relevant = [1, 0, 1, 1, 0]  # Ground truth relevance
predicted_relevant = [1, 0, 1, 0, 0]  # Predicted relevance

# Calculate metrics
precision = precision_score(true_relevant, predicted_relevant)
recall = recall_score(true_relevant, predicted_relevant)
f1 = f1_score(true_relevant, predicted_relevant)

print(f"Precision: {precision}")
print(f"Recall: {recall}")
print(f"F1 Score: {f1}")
API Documentation
The recommendation engine provides a simple API to get movie recommendations.

Endpoints
GET /recommend
Get movie recommendations based on a given movie title.

URL: /recommend
Method: GET
URL Params:
title=[string] (required) - The title of the movie for which to get recommendations.
Success Response:
Code: 200 OK
Content:
{
  "recommendations": ["Movie1", "Movie2", "Movie3"]
}
Error Response:
Code: 400 BAD REQUEST
Content:
{
  "error": "Movie title is required."
}
Example Request
curl -X GET "http://localhost:5000/recommend?title=3%20Idiots"
Example Response
{
  "recommendations": ["Taare Zameen Par", "PK", "Munna Bhai M.B.B.S."]
}
