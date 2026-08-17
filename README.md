# DIT637-TT06 

## Run Backend ExpressJS DB server
1. Copy your MongoDB Connection String from MongoDB Atlas
2. Create `.env` file and paste it after `MONGODB_URI=`
3. Open New Terminal
4. `cd backend-expressjs`
5. `npm install`
7. `npm run start`
8. Make the Port Visibility `Public`
9. Copy the forwarded address ExpressJS

## Run Backend FastAPI recommendation server
1. Create `.env` file and paste the forwarded address ExpressJS after `EXPRESSJS_BASE_URL=`
2. Open New Terminal
3. `cd backend-fastapi`
4. `pip install -r requirements.txt`
5. `uvicorn main:app --host 0.0.0.0 --port 8000`
6. Make the Port Visibility `Public`
7. Copy the forwarded address FastAPI

## Run Frontend React Native in the Mobile/Browser
1. Create `.env` file and paste the following:
- paste the forwarded address ExpressJS after  `API_URL_SEARCH=`
- paste the forwarded address FastAPI after `API_URL_RECOMMEND=`
2. Open New Terminal
3. `cd frontend-reactnative`
4. `npm install`
5. `npx expo login`
6. `npx expo start --tunnel` OR in the web `npx expo start --web`

## Key Snippet:

vectorizer = CountVectorizer()
feature_matrix = vectorizer.fit_transform(movie_features)

similarity_scores = cosine_similarity(
    selected_movie_vector,
    feature_matrix
)

top_indices = similarity_scores.argsort()[0][-3:][::-1]
recommendations = [movies[i] for i in top_indices]

## AI Prompt:

I am a student completing a technical lab on TT06 Experiencing ML. I have implemented a movie recommendation engine using FastAPI and Scikit-learn.

Based on this code snippet:

vectorizer = CountVectorizer()
feature_matrix = vectorizer.fit_transform(movie_features)

similarity_scores = cosine_similarity(
    selected_movie_vector,
    feature_matrix
)

top_indices = similarity_scores.argsort()[0][-3:][::-1]
recommendations = [movies[i] for i in top_indices]


## Summary:

The FastAPI recommendation service uses Scikit-learn to convert movie features such as genres and cast into numerical vectors and applies cosine similarity to identify movies with related characteristics. Separating this machine learning logic from the Express.js search service creates a modular microservices architecture that allows the recommendation component to be maintained and scaled independently. This design contributes to a Smart and Secure System by providing intelligent, data-driven recommendations while keeping application responsibilities separated and reducing unnecessary coupling between services.