# YouTube-Like Application with RabbitMQ

This project implements a simplified version of a YouTube-like application using RabbitMQ for communication between services. The application makes use of message queues to facilitate real-time notifications and asynchronous communication in a distributed system.

<img src="/diagram.jpg" width="550">


## Components

#### 1. YouTuber

The YouTuber service allows users to publish videos on the YouTube server. It sends messages containing the video name and the YouTuber’s name to the server.

#### 2. User

The User service allows users to subscribe or unsubscribe to YouTubers and receive real-time notifications whenever a YouTuber they subscribe to uploads a new video. Users communicate with the YouTube server to manage subscriptions and receive notifications.

#### 3. YouTube Server

The YouTube server consumes messages from both users and YouTubers, storing data, managing subscriptions, and sending notifications. It processes login, subscription, and unsubscription requests from users and handles video uploads from YouTubers.

## Setup and Installation

1. **Clone the Repository**
   ```bash
   git clone https://github.com/notkartikye/youtube-rabbitmq.git
   cd youtube-rabbitmq
    ```
2. **Start the Server:**
    ```bash
    python server.py
    ```

3. **Run a User Action:**
    ```bash
    python user.py <user_name> <action> <youtuber_name>
    ```

    > `<action>`: `s` to subscribe or `u` to unsubscribe

4. **Upload Content as a YouTuber:**
    ```bash
    python youtuber.py <creator_name> <content_name>
    ```

