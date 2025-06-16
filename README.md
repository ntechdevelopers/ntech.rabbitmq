# ntech.rabbitmq

This repository contains various examples demonstrating different messaging patterns using RabbitMQ with .NET/C#. The solution includes projects for:

*   **Standard Queue:** A basic queueing example.
*   **Worker Queue:** Demonstrates a work queue pattern where multiple consumers process tasks from a single queue.
*   **Publish/Subscribe:** Shows a publish/subscribe model where messages are broadcast to multiple subscribers.
*   **Direct Routing:** Illustrates message routing based on a routing key.

## Project Structure

The solution `Ntech.Rabbit/RabbitMQ.sln` contains the following key projects:

*   `Common`: A shared library for common models and utilities (e.g., message serialization).
*   `StandardQueue`: Producer and consumer for a standard message queue.
*   `WorkerQueue_Producer`: Produces messages for the worker queue.
*   `WorkerQueue_Consumer`: Consumes messages from the worker queue.
*   `PublishSubscribe_Publisher`: Publishes messages in a fanout exchange.
*   `PublishSubscribe_Subscriber`: Subscribes to messages from a fanout exchange.
*   `DirectRouting_Publisher`: Publishes messages with a routing key to a direct exchange.
*   `DirectRouting_Subscriber1`: Subscribes to messages with a specific routing key.
*   `DirectRouting_Subscriber2`: Subscribes to messages with another specific routing key.

## Setup and Running the Examples

To run these examples, you will need:

1.  **RabbitMQ Server:** Ensure you have a RabbitMQ server running. You can download it from [rabbitmq.com](https://www.rabbitmq.com/download.html) or run it via Docker.
2.  **Visual Studio (or compatible .NET IDE):** This solution is developed with Visual Studio.

### Steps to Run:

1.  **Clone the repository:**
    ```bash
    git clone https://github.com/ntechdevelopers/ntech.rabbitmq.git
    cd ntech.rabbitmq/Ntech.Rabbit
    ```
2.  **Restore NuGet Packages:** Open the `RabbitMQ.sln` file in Visual Studio. NuGet packages should restore automatically. If not, you can manually restore them via the Solution Explorer (right-click on the solution -> "Restore NuGet Packages").
3.  **Run Individual Projects:**
    *   Set the desired project (e.g., `WorkerQueue_Producer`, `WorkerQueue_Consumer`) as the startup project in Visual Studio.
    *   Run the producer project first, then the corresponding consumer project(s).
    *   For the Publish/Subscribe and Direct Routing examples, ensure all subscribers are running before the publisher to receive all messages.