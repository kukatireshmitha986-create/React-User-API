# React User API Application

A professional React application that retrieves user information from a REST API using React Hooks, `fetch()`, and `useEffect()`. The application demonstrates API integration, asynchronous data handling, loading states, error handling, and dynamic rendering of user information.

## 🌐 Live Demo

https://kukatireshmitha986-create.github.io/React-User-API/

## 📂 GitHub Repository

https://github.com/kukatireshmitha986-create/React-User-API

## 📸 Application Screenshot

![React User API Application](screenshots/react-user-api.png)

## 📌 Project Overview

The **React User API Application** is a frontend web application developed using React and Vite. It connects to the JSONPlaceholder REST API and dynamically retrieves a list of users.

The project was developed to demonstrate how React applications can communicate with external APIs using the `fetch()` method and manage asynchronous API requests using the `useEffect()` Hook.

The application provides a clean and responsive interface for displaying:

- User ID
- Name
- Username
- Email Address

It also provides appropriate feedback while data is being loaded and displays an error message if the API request fails.

## 🎯 Objectives

- Learn how to retrieve data from a REST API using `fetch()`.
- Understand the use of React's `useState()` Hook.
- Understand the use of React's `useEffect()` Hook.
- Handle asynchronous API requests.
- Display loading states while retrieving data.
- Handle API request failures gracefully.
- Dynamically render API data using React.
- Build a responsive and professional user interface.
- Deploy a Vite React application using GitHub Pages.

## 🚀 Features

- REST API integration
- Dynamic user data retrieval
- React `useState()` implementation
- React `useEffect()` implementation
- JavaScript `fetch()` API
- Loading state with `Loading...`
- Error handling
- Dynamic table rendering
- Responsive design
- Clean and professional user interface
- GitHub Pages deployment
- Automated deployment using GitHub Actions

## 🔗 API Used

This project uses the JSONPlaceholder Users API:

https://jsonplaceholder.typicode.com/users

The API provides sample user information in JSON format.

## 📊 Data Displayed

The application displays the following information for every user:

| Field | Description |
|---|---|
| ID | Unique user identification number |
| Name | Full name of the user |
| Username | User's username |
| Email | User's email address |

## ⚙️ React Concepts Used

### `useState()`

The `useState()` Hook is used to manage:

- User data
- Loading status
- Error messages

Example implementation:

    const [users, setUsers] = useState([]);
    const [loading, setLoading] = useState(true);
    const [error, setError] = useState("");

### `useEffect()`

The `useEffect()` Hook is used to execute the API request when the component is loaded.

Example:

    useEffect(() => {
      fetch("https://jsonplaceholder.typicode.com/users")
        .then((response) => {
          if (!response.ok) {
            throw new Error("Failed to fetch users");
          }
          return response.json();
        })
        .then((data) => {
          setUsers(data);
          setLoading(false);
        })
        .catch((error) => {
          setError(error.message);
          setLoading(false);
        });
    }, []);

### `fetch()`

The JavaScript `fetch()` API is used to retrieve user information from the external REST API.

## 🔄 Application Workflow

    User opens the React application
                ↓
        Users component loads
                ↓
        useEffect() executes
                ↓
        fetch() sends API request
                ↓
        JSONPlaceholder API
                ↓
        User data is received
                ↓
        setUsers() updates state
                ↓
        React renders user information
                ↓
        User List is displayed

If the request is still in progress:

    Loading...

If the request fails:

    Failed to fetch users

## 🛠️ Technologies Used

| Technology | Purpose |
|---|---|
| React | Frontend application development |
| JavaScript | Application logic and API handling |
| JSX | Component-based UI development |
| Vite | Development server and production build tool |
| HTML5 | Application structure |
| CSS3 | Styling and responsive design |
| REST API | Retrieving user information |
| Fetch API | Making HTTP requests |
| Git | Version control |
| GitHub | Source code hosting |
| GitHub Actions | Automated deployment |
| GitHub Pages | Application hosting |

## 📁 Project Structure

    React-User-API/
    │
    ├── .github/
    │   └── workflows/
    │       └── deploy.yml
    │
    ├── public/
    │
    ├── screenshots/
    │   └── react-user-api.png
    │
    ├── src/
    │   ├── components/
    │   │   └── Users/
    │   │       ├── Users.jsx
    │   │       └── Users.css
    │   │
    │   ├── App.jsx
    │   ├── App.css
    │   ├── index.css
    │   └── main.jsx
    │
    ├── .gitignore
    ├── index.html
    ├── package.json
    ├── package-lock.json
    ├── vite.config.js
    └── README.md

## 🧩 Component Structure

### Users Component

The main `Users` component is responsible for:

- Managing user data
- Calling the external API
- Managing loading status
- Handling errors
- Displaying user information
- Rendering the user list dynamically

Location:

    src/components/Users/Users.jsx

## ⏳ Loading State

While the API request is being processed, the application displays:

    Loading...

This provides feedback to the user and prevents the interface from appearing empty while the data is being retrieved.

## ❌ Error Handling

The application checks whether the API request was successful.

If the request fails, an error message is displayed instead of the user table.

This improves the reliability and user experience of the application.

## 📱 Responsive Design

The application uses responsive CSS so that the user table remains usable on different screen sizes, including:

- Desktop
- Laptop
- Tablet
- Mobile devices

Horizontal scrolling is supported for the table on smaller screens.

## 💻 Installation and Setup

### 1. Clone the Repository

    git clone https://github.com/kukatireshmitha986-create/React-User-API.git

### 2. Navigate to the Project

    cd React-User-API

### 3. Install Dependencies

    npm install

### 4. Start the Development Server

    npm run dev

### 5. Open the Application

Open the local URL shown by Vite, normally:

    http://localhost:5173/

## 🏗️ Production Build

To create a production-ready build:

    npm run build

The production files are generated inside:

    dist/

To preview the production build locally:

    npm run preview

## ☁️ Deployment

The application is deployed using **GitHub Pages** with **GitHub Actions**.

Deployment workflow:

    Source Code
        ↓
    GitHub Repository
        ↓
    GitHub Actions
        ↓
    npm install
        ↓
    npm run build
        ↓
    Vite generates dist/
        ↓
    GitHub Pages
        ↓
    Live Application

Live application:

https://kukatireshmitha986-create.github.io/React-User-API/

## 🔧 GitHub Pages Configuration

The Vite configuration uses the repository name as the deployment base path.

    base: "/React-User-API/"

This ensures that the generated JavaScript and CSS assets are correctly loaded when the application is hosted under the GitHub Pages project URL.

## 🤖 GitHub Actions

The project includes an automated deployment workflow:

    .github/workflows/deploy.yml

The workflow automatically:

1. Checks out the repository.
2. Sets up Node.js.
3. Installs project dependencies.
4. Builds the React application.
5. Uploads the Vite `dist` folder.
6. Deploys the application to GitHub Pages.

## 🧪 Testing

The application was tested for:

- Successful API connection
- User data retrieval
- User ID display
- Name display
- Username display
- Email display
- Loading state
- Error handling
- Responsive table layout
- Production build
- GitHub Pages deployment

The application successfully retrieves and displays the available users from the JSONPlaceholder API.

## 📋 Expected Output

The application displays a user table similar to:

| ID | Name | Username | Email |
|---:|---|---|---|
| 1 | Leanne Graham | Bret | Sincere@april.biz |
| 2 | Ervin Howell | Antonette | Shanna@melissa.tv |
| 3 | Clementine Bauch | Samantha | Nathan@yesenia.net |
| 4 | Patricia Lebsack | Karianne | Julianne.OConner@kory.org |
| 5 | Chelsey Dietrich | Kamren | Lucio_Hettinger@annie.ca |
| 6 | Mrs. Dennis Schulist | Leopoldo_Corkery | Karley_Dach@jasper.info |
| 7 | Kurtis Weissnat | Elwyn.Skiles | Telly.Hoeger@billy.biz |
| 8 | Nicholas Runolfsdottir V | Maxime_Nienow | Sherwood@rosamond.me |
| 9 | Glenna Reichert | Delphine | Chaim_McDermott@dana.io |
| 10 | Clementina DuBuque | Moriah.Stanton | Rey.Padberg@karina.biz |

## 🎓 Learning Outcomes

Through this project, the following concepts were practiced:

- React functional components
- React Hooks
- `useState()`
- `useEffect()`
- API integration
- REST APIs
- JavaScript `fetch()`
- Promises
- JSON data handling
- Conditional rendering
- Loading state management
- Error handling
- Array mapping in React
- Dynamic table generation
- Component-based architecture
- Responsive CSS
- Vite production builds
- Git and GitHub
- GitHub Actions
- GitHub Pages deployment

## 🔮 Future Enhancements

Possible future improvements include:

- Search users by name or username
- Filter users by email domain
- Pagination
- User detail pages
- Sorting functionality
- Refresh API button
- Skeleton loading animation
- Dark mode
- Improved accessibility
- Additional API information such as address, phone, and company details

## 📌 Project Information

**Project Name:** React User API Application

**Project Type:** React API Integration Project

**Frontend:** React + Vite

**API:** JSONPlaceholder

**Deployment:** GitHub Pages

**Automation:** GitHub Actions

**Repository:** https://github.com/kukatireshmitha986-create/React-User-API

**Live Demo:** https://kukatireshmitha986-create.github.io/React-User-API/

## 👩‍💻 Author

**Reshmitha Kukati**

AI & Data Science Student

GitHub: https://github.com/kukatireshmitha986-create

## ⭐ Conclusion

The **React User API Application** demonstrates how a modern React application can retrieve, manage, and dynamically display external API data. It provides practical implementation of `useState()`, `useEffect()`, `fetch()`, conditional rendering, loading states, and error handling while following a clean component-based structure.

The project is production-built using Vite and deployed through GitHub Actions to GitHub Pages, making it a complete example of React API integration from development to deployment.
