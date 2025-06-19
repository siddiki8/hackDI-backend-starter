# Hackathon Backend Starter - FastAPI Edition

Welcome to the Hackathon Backend Starter! This project is designed to give you a running start on building the backend for your hackathon project using FastAPI.

## Table of Contents

- [What is a Backend?](#what-is-a-backend)
- [What is FastAPI?](#what-is-fastapi)
- [What are REST APIs?](#what-are-rest-apis)
- [Getting Started](#getting-started)
  - [Prerequisites](#prerequisites)
  - [Installation](#installation)
- [Project Structure](#project-structure)
- [Connecting to Supabase](#connecting-to-supabase)
- [Setting up the Frontend](#setting-up-the-frontend)
- [Running the Server](#running-the-server)

## What is a Backend?

In a web application, the "backend" (also known as the "server-side") is the part of the application that is not visible to the user. It's responsible for all the logic that happens on the server, such as:

-   **Storing and retrieving data:** The backend communicates with a database (like Supabase) to store and retrieve information.
-   **User authentication and authorization:** The backend handles user logins, signups, and ensures that users can only access the data they are permitted to see.
-   **Business logic:** The backend contains the core logic of your application. For example, in an e-commerce app, the backend would handle processing orders, managing inventory, and calculating prices.
-   **Responding to requests from the frontend:** The backend exposes an API (Application Programming Interface) that the frontend can use to send and receive data.

In short, the backend is the engine of your web application, while the frontend is the user interface.

## What is FastAPI?

[FastAPI](https://fastapi.tiangolo.com/) is a modern, fast (high-performance), web framework for building APIs with Python 3.7+ based on standard Python type hints.

The key features are:

-   **Fast:** Very high performance, on par with **NodeJS** and **Go** (thanks to Starlette and Pydantic).
-   **Fast to code:** Increase the speed to develop features by about 200% to 300%.
-   **Fewer bugs:** Reduce about 40% of human-induced errors.
-   **Intuitive:** Great editor support. Completion everywhere. Less time debugging.
-   **Easy:** Designed to be easy to use and learn. Less time reading docs.
-   **Short:** Minimize code duplication. Multiple features from each parameter declaration.
-   **Robust:** Get production-ready code. With automatic interactive documentation.

## What are REST APIs?

A REST API (also known as a RESTful API) is an application programming interface (API or web API) that conforms to the constraints of REST architectural style and allows for interaction with RESTful web services. REST stands for **RE**presentational **S**tate **T**ransfer.

In simpler terms, a REST API is a way for different software applications to communicate with each other over the internet. When you use a web application, your browser (the frontend) sends requests to a server (the backend) to fetch or send data. A REST API defines the rules for how those requests should be structured.

Here are the key concepts of REST:

-   **Resources:** A resource is any piece of information that can be named. For example, in a blogging application, a user, a blog post, and a comment would all be resources. Each resource is identified by a unique URL (Uniform Resource Locator), like `/users/123` or `/posts/456`.
-   **HTTP Methods:** REST APIs use standard HTTP methods to perform actions on resources:
    -   `GET`: Retrieve a resource.
    -   `POST`: Create a new resource.
    -   `PUT` / `PATCH`: Update an existing resource.
    -   `DELETE`: Delete a resource.
-   **Stateless:** Each request from a client to a server must contain all the information needed to understand and complete the request. The server does not store any information about the client's state between requests.

## Getting Started

### Prerequisites

-   [Python 3.7+](https://www.python.org/downloads/)
-   A code editor (like [VS Code](https://code.visualstudio.com/))
-   A terminal or command prompt

### Installation

1.  **Clone the repository:**

    ```bash
    git clone https://github.com/your-username/hackDI-backend-starter.git
    cd hackDI-backend-starter
    ```

2.  **Create a virtual environment:**

    It's recommended to use a virtual environment to manage the project's dependencies.

    ```bash
    # On Windows
    python -m venv venv
    venv\Scripts\activate

    # On macOS/Linux
    python3 -m venv venv
    source venv/bin/activate
    ```

3.  **Install the dependencies:**

    ```bash
    pip install -r requirements.txt
    ```

4.  **Create your own `.env` file:**

    This project uses a `.env` file to store your Supabase credentials. Rename the `example.env` file to `.env` and add your Supabase URL and Key.

    ```bash
    # On Windows
    rename example.env .env

    # On macOS/Linux
    mv example.env .env
    ```

    Your `.env` file should look like this:

    ```
    SUPABASE_URL="YOUR_SUPABASE_URL"
    SUPABASE_KEY="YOUR_SUPABASE_KEY"
    ```

## Project Structure

```
.
├── app
│   └── main.py         # Your FastAPI application code
├── docs
│   ├── supabase_setup.md # Guide to setting up Supabase
│   └── react_frontend_setup.md # Guide to setting up the frontend
├── .env.example        # Example environment file
├── .gitignore          # Files to be ignored by Git
├── README.md           # This file
└── requirements.txt    # Project dependencies
```

## Connecting to Supabase

For a detailed guide on how to set up a Supabase project and connect it to this backend, please see the [Supabase Setup Guide](./docs/supabase_setup.md).

## Setting up the Frontend

For a guide on how to set up a React frontend to work with this backend, please see the [React Frontend Setup Guide](./docs/react_frontend_setup.md).

## Running the Server

Once you have everything set up, you can run the FastAPI server with the following command:

```bash
uvicorn app.main:app --reload
```

The `--reload` flag will automatically restart the server whenever you make changes to the code.

Now you can open your browser and go to [http://127.0.0.1:8000](http://127.0.0.1:8000) to see the "Hello, World!" message.

You can also access the interactive API documentation at [http://127.0.0.1:8000/docs](http://127.0.0.1:8000/docs). This documentation is automatically generated by FastAPI and allows you to test your API endpoints directly from the browser. 