-```
import socket
import threading

class MessagingSystem:
	def __init__(self):
		self.client_socket = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
		self.client_socket.connect(("localhost", 12345))
		self.username = input("Enter your username: ")

	def send_message(self):
		message = input("Enter your message: ")
		self.client_socket.send(f"{self.username}: {message}".encode())

	def receive_message(self):
		while True:
			message = self.client_socket.recv(1024).decode()
			print("New message received:", message)

	def run(self):
		send_thread = threading.Thread(target=self.send_message)
		receive_thread = threading.Thread(target=self.receive_message)
		send_thread.start()
		receive_thread.start()

messaging_system = MessagingSystem()
messaging_system.run()
``` 👋 Hi, I’m @Kami-art-sgd
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...

<!---
Kami-art-sgd/Kami-art-sgd is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
