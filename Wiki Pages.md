# General Introduction

Welcome to the culinary code app. The main goal of this application is to provide a way to manage your meals and groceries in a user-friendly way. This repo provides you with the necessary tools to do two out of our three intended uses:

- [ ] Utilize our own backend api with a small fee to utilize the services
- [x] Spin up your own backend api service and use your own openAI key for all AI services
- [x] Spin up your own backend api service, spin up a local LLM to replace the openAI services (success not guaratneed)   

To see what features the application currently has, visit [[Features]]

To see what features are currently planned, visit [[Planned_Features]]

To help develop these features, look at [[How_To]]


# Features

The application currently has the following features:

- Logging into a keycloak account
- Registering a new keycloak account
- Changing the username of the keycloak account
- Browsing recipes based on recipe names
- See recipe details
- Create new recipes based on a chatgpt prompt: supported identifiers include recipename, ingredients

# Planned Features

The application currently has the following features planned: 

- Browsing recipes based on ingredients, cooktime, difficulty, preferences
- Favoriting recipes
- Adding recipes to a mealplanner
- Viewing said mealplanner
- View a grocerylist based on planned meals
- Add items and ingredients to the grocerylist
- Managing Account settings: preferences that automatically get added to prompts, family size
- .... 

# Keycloak

- ## Set up

- ## Necessary Users

# Deploying to Azure

- ## Image generator

- ## GPT

- ## Blob storage

- ## Database

# Running everything locally

## Recommended LLM Model

After extensive testing, we recommend using the GPT-4o Mini model (version: 2024-07-18) for this project. This model has consistently delivered reliable and accurate results, meeting our specific requirements.

While we also tested GPT-3.5 Turbo, we found its reliability to be significantly lower, particularly in non-English languages. Since our development and testing focus on a Dutch-speaking user base, the GPT-4o Mini model proved far superior in handling these language-specific needs.

Additionally, we tested several local LLMs, but found that the output from smaller models was not reliable, with significant inconsistencies in performance. Larger models might offer better reliability, but they require significantly higher computational resources. Running them efficiently would demand high-end hardware, which may not be practical for all setups.

For users opting for local hosting, we recommend using an OpenAI model as the preferred option. Users can easily add their own OpenAI API key via the mobile app, enabling them to leverage the full reliability of OpenAI's models. The local LLM should only be used as a last resort, particularly due to the lower reliability and performance issues we encountered.


# Environment variables

- ## Frontend

- ## Backend

# Frontend

# Backend

# Roadmap

# Known Bugs

# Licenties

# How to 

- ## Set the project up

- ## Pull Request

- ## Report Bugs

- ## Ask questions
