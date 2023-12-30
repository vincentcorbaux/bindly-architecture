# Bindly: Book Recommendation App

Welcome to the Bindly repository! Bindly is a book recommendation app designed to provide users with personalized book suggestions. The app uses Google Firebase as its cloud solution to ensure a seamless and secure experience for book enthusiasts.

## What is Bindly

Bindly is an application created to provides new books recommendations to users using AI. It will use the tastes in literature of the user: the authors they like, the books they have read and like or dislike, the categories they are interested in.
Every Sunday, the users will receive 5 recommendations based on every interactions they had using the app.

## Architecture Overview

### General Schema

The architecture of Bindly consists of a Flutter application connected to two services on Google Firebase: Authentification and Firestore Database.

Once registred in the Authentification database, a user can then uses the application, which will write/creates/deletes documents on the Firestore document for this user

### How did we design our architecture?

Our final architecture incorporates five applications connected to two databases. For a deep dive into our design decisions, refer to the section on "How did we design our architecture?".

### The Prediction

Initially, our approach involved predicting all user-requested URLs. However, due to the time and resource costs associated with network catching and predictions, we opted for a faster and more efficient system.

### Saving Old Predictions

To enhance speed and efficiency, we implemented two databases to store rejected and accepted URLs, preventing redundant predictions and minimizing impact on the user.

### Refitting our AI

Continuous improvement of our AI is crucial. We introduced a refitting process that involves storing network packets from unknown URLs in AWS DynamoDB.

## Contributors

- **Vincent CORBAUX:**
  - GitHub: [@vincentcorbaux](https://github.com/vincentcorbaux)

- **Benjamin CHOMMAUX:**
  - GitHub: [@benjaminchommaux](https://github.com/benjaminchommaux)

- **Romane BARD:**
  - GitHub: [@romanebard](https://github.com/romanebard)

A big thank you to all our contributors! 🚀
