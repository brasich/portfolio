---
title: "Baby's First Azure Function"
date: 2021-12-15T20:38:13-05:00
draft: false
---

Our team practices a fairly standard separation of responsibilities between Data Science and Engineering. On the data science side, I take in requirements from the business, frame those requirements into a tractable problem, and build a model using all available data. Outside of the model build itself, though, I rely on close partnership with engineers to make data available for me in the production environment and serve up predictions to clients through some sort of production infrastructure.

Our engineering team often uses Azure Functions for data processing and for serving models. After a year of hearing that term thrown around, I decided it was time to try it out for myself to see what all the fuss is about. How can one tool be used for so much?

### What is an Azure Function?

From Microsoft themselves, an Azure function is "an event-driven, serverless compute platform that helps solve complex orchestration problems". There are a couple of important terms in there:
+ **Event-driven:** function apps are called when some event occurs, like an HTTP request to the app's endpoint.
+ **Serverless:** rather than having to specify or even think about required instance sizes, compute resources allocated to function apps scale dynamically based on demand.

Also of note is that Azure functions are intended to be stateless, that is they are intended to perform a specific action on an input and provide an output with no interactions across multiple requests. 

### Experimenting with Azure

Like most of the major cloud providers, Azure includes a free tier to allow new users to experiment for up to a year with all the platform's tools. I made myself a new account and jumped right into [one of their quickstart tutorials](https://docs.microsoft.com/en-us/azure/azure-functions/create-first-function-cli-python?tabs=azure-cli%2Cbash%2Cbrowser) to create a function app written in Python.

Working through this tutorial was massively illustrative - at their core, Azure functions are extremely simple. When GET or POST request is recieved by the function's endpoint, it executes a function, `main(req: func.HttpRequest)` within `__init__.py`. The request can contain inputs within the query parameters or json in the body. Using those inputs, we can do any required processing and do something like run the inputs through a model, do some data cleaning, etc. Any additional packages we rely on for data science tasks like `pandas`, `scikit-learn`, etc. can be installed in the cloud runtime from `pip` simply by adding them to `requirements.txt`

For the most common data science and data engineering tasks, this looks something like:

| **Application** | **Input** | **Output** |
| --- | --- | --- |
| Prediction API | Feature values | Model-derived prediction in an HTTP response |
| Data processing | Raw data | Cleaned/processed data stored in a database | 

The delineation between these applications aren't completely cut and dry - a prediction API can do some real-time feature processing, for example - but the story remains that Azure functions are a great choice for every part of a production data science workflow. Even through this quick exercise I can see why our team likes using them so much.

[See code here](https://github.com/brasich/my-first-azure-function)  
