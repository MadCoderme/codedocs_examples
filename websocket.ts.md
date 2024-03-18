### Table of Contents

1. [Introduction](#introduction)
2. [Server Configuration](#server-configuration)
3. [HTTP Request Handling](#http-request-handling)
4. [WebSocket Handling](#websocket-handling)
5. [Server Startup](#server-startup)

---

## Introduction

This document provides an overview of the Bun server code and its functionalities. The code utilizes Bun's built-in capabilities to handle both HTTP requests and WebSocket connections.

## Server Configuration

The server is configured using `Bun.serve` and accepts an object with two main properties: `fetch` and `websocket`. 

* **`fetch(req, server)`:** This function handles incoming HTTP requests. It receives the request object (`req`) and the server instance (`server`) as arguments.
* **`websocket`:** This object defines the behavior for WebSocket connections. It contains a `message` function that is called whenever a message is received from a connected client.

## HTTP Request Handling

The `fetch` function is responsible for processing HTTP requests. In this code, it first attempts to upgrade the connection to a WebSocket using `server.upgrade(req)`. 

* If the upgrade is successful, Bun automatically sends a `101 Switching Protocols` response and the `fetch` function returns `undefined`. 
* If the upgrade fails, the function proceeds to handle the request as a regular HTTP request and returns a new `Response` object with the content "Hello world!".

## WebSocket Handling

The `websocket.message` function is triggered whenever a message is received from a connected WebSocket client. It takes two arguments: the WebSocket object (`ws`) and the received message (`message`). 

This function performs the following actions:

1. Logs the received message to the console.
2. Sends a response back to the client with the content "You said: {message}", where {message} is replaced with the actual received message.

## Server Startup

After defining the server configuration, the code starts the server and logs a message to the console indicating the hostname and port on which the server is listening. 
