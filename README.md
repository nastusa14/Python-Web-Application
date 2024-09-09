# Python Web Application
This program is a Python-based web application that allows users to send messages through a web interface. The application consists of two main components: an HTTP server and a Socket server, which run concurrently using threads.

Description

HTTP Server

Port: The HTTP server runs on port 3000.

Routing:

/ - Serves the index.html file, which is the main web page.

/message - Serves the message.html file, where users can submit messages along with their username.

Static files: The server also handles static resources like style.css and logo.png.

Error handling: If a user navigates to a non-existent route, the server returns the error.html page with a 404 status code.

Socket Server

Port: The Socket server listens on port 5000 using the UDP protocol.

Functionality:

The HTTP server sends form data (username and message) to the Socket server.
The Socket server receives the data, processes it, and stores it in a data.json file inside the storage directory.
Each entry in data.json is timestamped with the time the message was received.

Data Storage

The messages are stored in storage/data.json. The file has a format where each entry is a dictionary with the timestamp as the key, and the message details (username and message) as the value.

Example of data.json Format:

{
  "2024-09-09T12:34:56.789012": {
    "username": "john_doe",
    "message": "Hello, world!"
  },
  "2024-09-09T12:35:22.123456": {
    "username": "jane_doe",
    "message": "Second message"
  }
}

How to Run

Ensure that you have Python 3 installed on your machine.

Place the following files in the same directory as the main.py file:

index.html (main webpage)

message.html (message submission page)

error.html (error page for 404 responses)

style.css (CSS file for styling)

logo.png (logo image)

Create a storage directory and ensure that a data.json file exists within it (an empty JSON file).

Run the main.py script:

python main.py

Open a web browser and navigate to http://localhost:3000/ to view the main page.

Dependencies

Python 3.x (Standard Library)
No additional external dependencies are required for this program.

License

This project is licensed under the MIT License.
