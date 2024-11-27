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

  When you have the docker image running locally or in the cloud, go to the address provided in the docker compose file or the url in the cloud. You should see a login screen.
  1. Log in as admin. In the provided docker file the name and password are both admin but it is recommended to change those values
  2. On the top left you should see a dropdown menu that is currently set to the master realm
  3. Click on that dropdown menu and create a new realm
  4. In the json input field, select import from file and select the provided realm-export.json file in the location where you downloaded this project
  5. You should now have a new realm, you can change the name of this realm for security purposes but be aware that you will need to change environment variables. see [[Environment_Variables]]

- ## Necessary Users
  1. Go to the user tab, this should be visible on the left hand side
  2. Create a new user. This will become the admin user with rights to create new accounts.
  3. After creation of the user, go to the credentials tab of that user (at the top) and create a new password. Set "temporary" to off.
  4. Go to the role management tab of the user (at the top)
  5. Give the user the following roles:
        - realm-admin
        - manage-account-links
        - manage-account
        - view-profile
  6. The user should be all set up

# Deploying to Azure

- ## Image generator

- ## GPT

- ## Blob storage

- ## Database

# Running everything locally

## Running docker

Explain docker here...

## Recommended LLM Model

After extensive testing, we recommend using the GPT-4o Mini model (version: 2024-07-18) for this project. This model has consistently delivered reliable and accurate results, meeting our specific requirements.

While we also tested GPT-3.5 Turbo, we found its reliability to be significantly lower, particularly in non-English languages. Since our development and testing focus on a Dutch-speaking user base, the GPT-4o Mini model proved far superior in handling these language-specific needs.

Additionally, we tested several local LLMs, but found that the output from smaller models was not reliable, with significant inconsistencies in performance. Larger models might offer better reliability, but they require significantly higher computational resources. Running them efficiently would demand high-end hardware, which may not be practical for all setups.

For users opting for local hosting, we recommend using an OpenAI model as the preferred option. Users can easily add their own OpenAI API key via the mobile app, enabling them to leverage the full reliability of OpenAI's models. The local LLM should only be used as a last resort, particularly due to the lower reliability and performance issues we encountered.


# Environment variables

- ## Frontend
  - KEYCLOAK_BASE_URL: Start of the keycloak url appended before any calls made to keycloak. Example for local development: "http://localhost:8180"
  - KEYCLOAK_CLIENT_ID: Name of your keycloak client. Example: "flutter-app"
  - KEYCLOAK_REALM: Name of your keycloak realm. Example: "culinary-code-dev-realm"
  - BACKEND_BASE_URL: Start of the backend url appended before any calls made to the backend api endpoints. Example for local development: "https://localhost:7098"
  
- ## Backend
  - AZURE_OPENAI_API_KEY: OpenAI api key for the openAI services running in Azure.
  - AZURE_OPENAI_ENDPOINT: Start of the azure openAI services url appended before any call made to these services.
  - AZURE_STORAGE_CONNECTION_STRING: Connectionstring for the blob storage running in Azure.
  - AZURE_STORAGE_CONTAINER_NAME: Container name for the blob storage running in Azure.
  - KEYCLOAK_BASE_URL: Start of the keycloak url appended before any calls made to keycloak. Example for local development: "http://localhost:8180"
  - KEYCLOAK_CLIENT_ID: Name of your keycloak client. Example: "flutter-app"
  - KEYCLOAK_REALM: Name of your keycloak realm. Example: "culinary-code-dev-realm"
  - KEYCLOAK_ADMIN_USERNAME: name of the admin with rights to create new accounts.
  - KEYCLOAK_ADMIN_PASSWORD: name of the password for the admin account mentioned above.
  - DATABASE_JOB_MIN_AMOUNT: amount of recipes should always be in the database. At 2 am the program will remove recipes that went unused for 31 days and are not saved in favourites. After it will fill the database back up with newly generated recipes up till this value. Example value: "100"

# Frontend

## Language

We have opted to build our frontend in flutter. The goal was to build a multiplatform application which flutter lends itself to incredibly well. 
To make this choice we have looked at: Flutter, React Native, Kotlin and Jetpack compose.
After a brief search we concluded Jetpack compose was not suited for the goal of a multiplatform application.


# Backend

# Roadmap

# Known Bugs

# Licences
  - Apache2.0
  - Moq diff license

# How to 

- ## Set the project up

- ## Pull Request

- ## Report Bugs

- ## Ask questions
