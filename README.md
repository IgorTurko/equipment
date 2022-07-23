# Test assignment summary:
This repo contains no code and only an explanation for the completed work within the project.
This project consists of 3 parts:
- Api service https://github.com/IgorTurko/equipment-api;
- Frontend https://github.com/IgorTurko/equipment-web;
- AWS hosting http://equipment-web.s3-website.eu-north-1.amazonaws.com;

# Obstacales
I finished this test assignment with one week delay. I don't think that with 2-3hours a day one week is plausible for this assignment. In the beginning, I used Elastic Beanstalk but in the end, I gave up and switched to EC2 Instance for the API.

# Screenshots
<img width="826" alt="image" src="https://user-images.githubusercontent.com/4738307/180428044-880e0f13-2070-49b3-aae4-bebd60ede388.png">
<img width="614" alt="image" src="https://user-images.githubusercontent.com/4738307/180428111-49dc723a-b682-4ccf-bca6-eee59260278e.png">
<img width="633" alt="image" src="https://user-images.githubusercontent.com/4738307/180428321-128839cc-7b5a-46fe-92f0-44aca7bcf451.png">


# Api
I decided to use Nodejs and Fastify as a web framework. You can read about Fastify [here](https://www.fastify.io). The main advantage for me is that Fastify can guarantee data contract for requests and responses also it supports Typescript which makes the development process less buggy.

#### What was done?
- API for fetching equipment list: `GET /v1/equipment?limit={}`;
- API for fetching a single equipment item by code: `GET /v1/equipment/:code`;
- API for saving new equipment item: `POST /v1/equipment`;
- Unit tests for all APIs;
- MongoDb Atlas hosted;
- AWS Instance created and configured;

#### TODO: 
- Add [swagger plugin](https://github.com/fastify/fastify-swagger) for serving a Swagger UI automatically generated from your route schemas;
- Change approach for storing credentials in the repo. For example, one bad thing I've done is saving the DB connection directly in the `.env` file. I think that the better approach could be using something like [ejson](https://github.com/Shopify/ejson) for managing a collection of secrets in source control;
- Also, the deployment pipeline could/should be automated;
- Also adding a docker container for running this app could be a good idea as well;

# Frontend
Create react app was used, as it contains everything for fast development. [Chakra UI](https://chakra-ui.com/) was chosen as a UI library. Chakra UI provides a set of accessible, reusable, and composable React components that make it easy to create react pages. Also [storybook](https://storybook.js.org) for testing component's look and feel. One interesting library I use in this project is [io-ts](https://github.com/gcanti/io-ts) for runtime types decoding/engoding, when there is a need to validate data from other services/api (equipment-api) this library is very convinient.

#### What was done?
- A page for listing equipment;
- A page for equipment item details;
- A page for creating a new equipment item;
- Unit tests for API and several components;
- Storybook for all dummy components (except pages);

#### TODO: 
- Cover all components with unit tests;
- Improve mobile responsiveness (for example navigation bar is not responsive);
