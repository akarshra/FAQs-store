# FAQs-store
A Django-based FAQs store with multilingual support using Python. It features a structured model for storing translations, a REST API for fetching localized content, and a WYSIWYG editor for rich-text answers.
Table of Contents
Features
Installation
Environment Setup
Usage
API Endpoints
Testing
Docker Deployment (Bonus)
Contribution Guidelines
License
Features
CRUD Operations: Create, read, update, and delete FAQs.
Multi-language Support: Store FAQs in multiple languages (e.g., English, Hindi, Bengali).
Redis Caching: Cache GET requests for improved performance.
Unit Tests: Written with Mocha, Chai, and Supertest.
Docker Support: Easily containerize and deploy the application.
Installation
Clone the Repository:

git clone https://github.com/your-username/faq-backend.git
cd faq-backend
Install Dependencies:

npm install
Environment Setup
Create a .env file in the root directory of the project and add the following (adjust values as necessary):

PORT=3000
MONGODB_URI=mongodb+srv://<username>:<password>@cluster0.yourcluster.mongodb.net/faqDB?retryWrites=true&w=majority
Note: Replace <username>, <password>, and yourcluster with your actual MongoDB Atlas connection details. Also, ensure that Redis is installed and running on its default port (6379).

Usage
To start the server locally:

npm start
The API will run on http://localhost:3000.

API Endpoints
GET /api/faqs
Description: Retrieve all FAQs.

Usage Example:

curl http://localhost:3000/api/faqs
POST /api/faqs
Description: Create a new FAQ.

Payload Example:

{
  "question": "What is Node.js?",
  "answer": "A JavaScript runtime built on Chrome's V8 engine.",
  "question_hi": "Node.js क्या है?",
  "answer_hi": "Chrome के V8 इंजन पर आधारित एक JavaScript रनटाइम है."
}
Usage Example:

curl -X POST http://localhost:3000/api/faqs \
     -H "Content-Type: application/json" \
     -d '{
           "question": "What is Node.js?",
           "answer": "A JavaScript runtime built on Chrome\'s V8 engine.",
           "question_hi": "Node.js क्या है?",
           "answer_hi": "Chrome के V8 इंजन पर आधारित एक JavaScript रनटाइम है."
         }'
Other endpoints (PUT, DELETE, etc.) can be implemented similarly if needed.

Testing
Unit tests are written with Mocha, Chai, and Supertest. To run the tests, execute:

npm test
The tests will cover the GET and POST endpoints and validate that the API is functioning correctly.

Docker Deployment (Bonus)
This project includes a Dockerfile and docker-compose.yml for containerized deployment.

Dockerfile
The Dockerfile sets up the Node.js environment, installs dependencies, and starts the application.

docker-compose.yml
The docker-compose.yml file defines two services:

app: The Node.js application.
redis: The Redis server.
To build and run the Docker containers:

docker-compose up --build
After the build completes, your API will be available at http://localhost:3000.

Contribution Guidelines
Fork the Repository: Create your own fork.
Create a Branch: Use a feature or bugfix branch for your changes.
Write Tests: Ensure that new features or bug fixes are covered by unit tests.
Submit a Pull Request: Provide a detailed description of your changes.
Please follow standard Git commit practices and maintain code quality with ESLint.

License
This project is licensed under the MIT License.
