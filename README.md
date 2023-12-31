

# Bindly: Book Recommendation App

Welcome to the Bindly repository! Bindly is a book recommendation app designed to provide users with personalized book suggestions. The app uses Google Firebase as its cloud solution to ensure a seamless and secure experience for book enthusiasts.

## Table of contents

- [What is Bindly](#what-is-bindly)
- [Architecture Overview](#architecture-overview)
  - [General Schema](#general-schema)
  - [Why Firebase?](#why-firebase-)
  - [Overview of Firebase Firestore database](#overview-of-firebase-firestore-database)
  - [How did we design our architecture?](#how-did-we-design-our-architecture)
- [The Predictions](#the-predictions)
  - [Ratings](#ratings)
  - [Saving Old Predictions](#saving-old-predictions)
- [Advantages of Our Architecture](#advantages-of-our-architecture)
- [Contributors](#contributors)


## What is Bindly

Bindly is an application created to provides new books recommendations to users using AI. It will use the tastes in literature of the user: the authors they like, the books they have read and like or dislike, the categories they are interested in.
Every Sunday, the users will receive 5 recommendations based on every interactions they had using the app.

## Architecture Overview

### General Schema

The architecture of Bindly consists of a Flutter application connected to two services on Google Firebase: Authentification and Firestore Database.

Once registred in the Authentification database, a user can then uses the application, which will write/creates/deletes documents on the Firestore document for this user.

<img width="1226" alt="Screenshot 2023-12-31 at 14 42 13" src="https://github.com/vincentcorbaux/bindly-architecture/assets/110817242/2df8fd0b-c891-4e4a-8b8d-3ebfd98c9e5a">

### Why Firebase ?

Firebase is a great cloud solution for Bindly, due to its versatility and ease of integration. Firebase offers a comprehensive suite of services, including authentication, hosting, and cloud functions. Its seamless integration with Flutter mobile applications ensures a smooth and efficient development process. The Firestore databases allows Bindly to dynamically update book recommendations based on user interactions. Additionally, Firebase Authentication provides a secure and hassle-free user login experience. The scalability of Firebase accommodates the growing user base of Bindly, while its intuitive console simplifies monitoring and management. Overall, Firebase empowers Bindly to deliver a reliable, scalable, and feature-rich book recommendation experience to users.

### Overview of Firebase Firestore database

<img width="1039" alt="Screenshot 2023-12-31 at 14 32 32" src="https://github.com/vincentcorbaux/bindly-architecture/assets/110817242/73110dc7-6bec-4859-ac53-f56c02620f62">


### How did we design our architecture?

The goal of our application is to store the maximum of informations the user is going to provide us so we can after use them for the recommendations. Hence the decomposition in "documents" of the Firestore collections was the best alternative for our project. As you can see on the above schema, each user's interations are stored in a user document in the "Users" collection, and then divided into other collections so it's easy to retrieve them after.

## The Predictions

### Ratings

Our predictions are based on every like and dislike the user is going to inform us. 
To store these informations, we created a dedicated Firestore collection called "User's rating". Depending on if the book is rated, liked or put in favorites, the corresponding genre and author of this book will receive a certain score:
- +3 if rated positive
- +2 if put in favorite
- +1 if liked via swipe
- -1 if dislike via swipe
- -3 if rated negative

This system allows us to quickly retrieve which category and author are the most appropriate for the user and then give them adequate recommendations.

### Saving Old Predictions

Once the algorithm has retrieved the weekly recommendations for the user, they are stored in the "Recommendations" collection. Hence, our application just has to take the most recent recommendations to the user. It allows us to have a quick and easy way to retrive information, reducing delay in the user experience. 

## Avantages of our Architecture
The combination between Firebase and the different collections we have created ensures a smooth user's experience. 
About the cost, Firestore bills after a certain number of documents written/read/deleted. Hence, it was important for us to minimize these interactions with the database.

## Contributors

- **Vincent CORBAUX:**
  - GitHub: [@vincentcorbaux](https://github.com/vincentcorbaux)

- **Benjamin CHOMMAUX:**
  - GitHub: [@benjaminchommaux](https://github.com/benjaminchommaux)

- **Romane BARD:**
  - GitHub: [@romanebard](https://github.com/romanebard)

A big thank you to all our contributors! 🚀
