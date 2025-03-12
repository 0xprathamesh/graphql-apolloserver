# GraphQL Todo App

A modern todo list application built with GraphQL, Apollo Server, Next.js, and Tailwind CSS. This application demonstrates how to build a full-stack application with GraphQL as the API layer.

<img width="1435" alt="Screenshot 2025-03-12 at 11 22 25 PM" src="https://github.com/user-attachments/assets/69a452b2-b98d-4897-bed1-faf58ff97199" />


## Features

- GraphQL API with Apollo Server
- Next.js frontend with App Router
- React components with Tailwind CSS for styling
- Apollo Client for data fetching
- Todo list with user associations
- Clean, responsive UI

## Tech Stack

- **Backend**:
  - Express.js
  - Apollo Server
  - GraphQL

- **Frontend**:
  - Next.js 14
  - React
  - Apollo Client
  - Tailwind CSS
  - Geist font family

## Project Structure

```
graphql-todo/
├── server/
│   ├── index.js         # Apollo Server setup
│   ├── todos.js         # Todo data
│   └── user.js          # User data
├── app/
│   ├── apolloClient.js     # Apollo Client provider
│   ├── page.js          # Main todo list page
│   ├── layout.js        # Root layout with fonts
│   └── globals.css      # Global styles
├── public/
└── package.json
```

## Getting Started

### Prerequisites

- Node.js 18.x or higher
- npm or yarn

### Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/graphql-todo.git
   cd graphql-todo
   ```

2. Install dependencies:
   ```bash
   # Install server dependencies
   cd server
   npm install

   # Install client dependencies
   cd ..
   npm install
   ```

### Running the Application

1. Start the GraphQL server:
   ```bash
   # From the server directory
   npm run start
   # or
   node index.js
   ```
   The GraphQL server will run on http://localhost:5001/graphql

2. Start the Next.js application:
   ```bash
   # From the project root
   npm run dev
   ```
   The application will be available at http://localhost:3000

## GraphQL Schema

```graphql
type User {
    id: ID!
    name: String!
    username: String!
    email: String!
    phone: String!
    website: String!
}

type Todo {
    id: ID!
    title: String!
    completed: Boolean
    user: User
    userId: ID!
}

type Query {
    getTodos: [Todo]
    getAllUsers: [User]
    getUser(id: ID!): User
}
```

## API Endpoints

- **GraphQL Endpoint**: `http://localhost:5001/graphql`
- **Available Queries**:
  - `getTodos`: Get all todos with user information
  - `getAllUsers`: Get all users
  - `getUser(id: ID!)`: Get a specific user by ID

## Frontend Components

The main components of the application are:

- **Providers**: Client component that provides Apollo context
- **Home**: The main todo list page displaying todos with user information

## Deployment

### Backend Deployment

1. Set up environment variables for production:
   ```
   PORT=5001
   NODE_ENV=production
   ```

2. Deploy to your preferred hosting service (Heroku, Vercel, AWS, etc.)

### Frontend Deployment

1. Build the application:
   ```bash
   npm run build
   ```

2. Deploy to Vercel, Netlify, or your preferred hosting service.

## Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Acknowledgments

- [Apollo GraphQL](https://www.apollographql.com/)
- [Next.js](https://nextjs.org/)
- [Tailwind CSS](https://tailwindcss.com/)
- [JSONPlaceholder](https://jsonplaceholder.typicode.com/) for the initial todo and user data structure
