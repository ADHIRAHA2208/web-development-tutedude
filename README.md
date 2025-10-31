# To-Do List Full-Stack Application

A full-stack To-Do List application built with Node.js, Express.js, MongoDB, and React.

## Features

- Create, read, update, and delete tasks
- Mark tasks as completed/incomplete
- Search tasks by title or description
- Responsive React frontend
- RESTful API backend with validation and error handling

## Tech Stack

### Backend
- Node.js
- Express.js
- MongoDB with Mongoose
- Express Validator for input validation

### Frontend
- React
- Axios for API calls
- CSS for styling

## Prerequisites

- Node.js (v14 or higher)
- MongoDB (local installation or MongoDB Atlas)
- npm or yarn

## Installation and Setup

### Backend Setup

1. Navigate to the backend directory:
   ```bash
   cd backend
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Create a `.env` file in the backend directory with the following content:
   ```
   MONGO_URI=mongodb://localhost:27017/todo-list
   PORT=5000
   ```
   - Replace `mongodb://localhost:27017/todo-list` with your MongoDB connection string if using MongoDB Atlas.

4. Start the backend server:
   ```bash
   npm run dev
   ```
   The server will run on `http://localhost:5000`.

### Frontend Setup

1. Navigate to the frontend directory:
   ```bash
   cd frontend
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Create a `.env` file in the frontend directory with the following content:
   ```
   REACT_APP_API_URL=http://localhost:5000/api
   ```
   - Update the URL if your backend is running on a different port or host.

4. Start the React development server:
   ```bash
   npm start
   ```
   The app will open in your browser at `http://localhost:3000`.

## API Endpoints

### Tasks

- `GET /api/tasks` - Get all tasks
- `GET /api/tasks/:id` - Get a specific task by ID
- `POST /api/tasks` - Create a new task
- `PUT /api/tasks/:id` - Update a task
- `DELETE /api/tasks/:id` - Delete a task
- `PATCH /api/tasks/:id/status` - Update task completion status
- `GET /api/tasks/search?q=query` - Search tasks

### Request/Response Examples

#### Create Task
```json
POST /api/tasks
{
  "title": "Buy groceries",
  "description": "Milk, bread, eggs"
}
```

#### Update Task
```json
PUT /api/tasks/:id
{
  "title": "Buy groceries",
  "description": "Milk, bread, eggs, cheese",
  "completed": false
}
```

#### Update Task Status
```json
PATCH /api/tasks/:id/status
{
  "completed": true
}
```

## Testing with Postman

1. Import the API endpoints into Postman.
2. Set the base URL to `http://localhost:5000/api`.
3. Test each endpoint with appropriate request bodies.

## Deployment

### Backend Deployment (Render)

1. Create a Render account and connect your GitHub repository.
2. Create a new Web Service.
3. Set the build command to `npm install`.
4. Set the start command to `npm start`.
5. Add environment variables in Render dashboard:
   - `MONGO_URI`: Your MongoDB Atlas connection string
   - `PORT`: 10000 (or Render's default)
6. Deploy the service.

### Frontend Deployment (Netlify)

1. Create a Netlify account and connect your GitHub repository.
2. Set the build command to `npm run build`.
3. Set the publish directory to `build`.
4. Add environment variable:
   - `REACT_APP_API_URL`: Your deployed backend URL (e.g., `https://your-backend.onrender.com/api`)
5. Deploy the site.

## Project Structure

```
todo-list/
├── backend/
│   ├── controllers/
│   │   └── taskController.js
│   ├── middleware/
│   │   └── errorHandler.js
│   ├── models/
│   │   └── Task.js
│   ├── routes/
│   │   └── tasks.js
│   ├── services/
│   │   └── taskService.js
│   ├── .env
│   ├── package.json
│   └── server.js
├── frontend/
│   ├── public/
│   ├── src/
│   │   ├── components/
│   │   │   ├── TaskForm.js
│   │   │   ├── TaskItem.js
│   │   │   ├── TaskList.js
│   │   │   └── SearchBar.js
│   │   ├── App.css
│   │   ├── App.js
│   │   └── index.js
│   ├── .env
│   └── package.json
├── README.md
└── TODO.md
```

## Challenges Faced

1. **MongoDB Connection**: Ensuring proper connection setup for both local and cloud deployments.
2. **CORS Issues**: Configuring CORS middleware to allow frontend-backend communication.
3. **State Management**: Implementing efficient state updates in React for real-time UI changes.
4. **Error Handling**: Creating comprehensive error handling for both frontend and backend.
5. **Validation**: Implementing input validation on both client and server sides.

## Contributing

1. Fork the repository.
2. Create a feature branch.
3. Make your changes.
4. Test thoroughly.
5. Submit a pull request.

## License

This project is licensed under the MIT License.


deploymnet link 

rakshada5.netlify.app
