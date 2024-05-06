# Muhammad Sean Arsha Galant 2206822963 - Tutorial 10 Part 2
## Reflection

### Experiment 2.1: Original code, and how it run

Server
![alt text](<assets/Screenshot 2024-05-06 134730.png>)
Client 1
![alt text](<assets/Screenshot 2024-05-06 134739.png>)
Client 2
![alt text](<assets/Screenshot 2024-05-06 134745.png>)
Client 3
![alt text](<assets/Screenshot 2024-05-06 134753.png>)

To run one server and three clients, I opened three terminals (powershell) for the clients and 1 more terminal for the server. Afterwards, I started the server first by running `cargo run --bin server`, and then executed each of the clients one-by-one using `cargo run --bin client`. Then, in each of the clients I typed in a message which shows an output from all 3 clients in each of the clients and the server. When a client, such as Client 1, types a message, like "This is from client 1", and sends it to the server, the server acknowledges receipt of the message and broadcasts it to all other connected clients, including Client 2 and Client 3. Similarly, when Client 2 or Client 3 enters their respective messages, such as "This is from client 2" or "This is from client 3", the server ensures that these messages are distributed to all other clients in the chat. Consequently, all clients, including the one that sent the original message, receive broadcasted messages from the server, facilitating a synchronized communication environment where participants can engage in real-time conversations.

Conversely, upon successful startup, the server confirms its readiness by displaying a message indicating that it is listening on port 2000. As clients connect to the server, it logs each new connection, indicating the IP address and port number of the client. For instance, the server logs the establishment of connections from three different clients, identified by their IP addresses: 127.0.0.1. Additionally, the server displays messages received from each client, attributing them to the respective client's IP address. This demonstrates the server's ability to receive and process messages from multiple clients concurrently. 

### Experiment 2.2: Modifying port

To modify the port to 8080 in the server-side code and ensure it runs properly, we need to update the server's listening port in the main() function of the server.rs file. Additionally, we should ensure that the clients connect to the correct port. After updating the server to listen on port 8080, we need to ensure that the clients also connect to the same port. The WebSocket protocol used for communication is defined in the tokio_websockets crate, specifically in the ClientBuilder and ServerBuilder implementations.By updating both the server and client code to use port 8080, we ensure that they communicate over the same port, enabling proper interaction between the server and clients.