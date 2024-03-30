# Laravel Vue CRUD App

Welcome to the Laravel Vue CRUD App, a web application built with Laravel for the backend, Vue.js for the frontend, and an API connection for seamless data management. This project aims to provide a user-friendly interface for performing CRUD operations on your data.

## Features
- **Create, Read, Update, Delete**: Perform CRUD operations on your data with ease.
- **Laravel Backend**: Built on the powerful Laravel framework for robust backend functionality.
- **Vue.js Frontend**: Utilizes Vue.js for a dynamic and responsive user interface.
- **API Connection**: Connects the frontend and backend for efficient data communication.

## Installation
1. Clone the repo: `git clone https://github.com/farazkhan2000/crud_app.git`
2. Navigate to the project directory: `cd crud_app`
3. Install PHP dependencies: `composer install`
4. Install Node.js dependencies: `npm install`
5. Configure environment variables: Copy `.env.example` to `.env` and update database credentials.
6. Generate application key: `php artisan key:generate`
7. Migrate the database: `php artisan migrate`
8. Compile frontend assets: `npm run dev` or `npm run prod` for production.
9. Start the development server: `php artisan serve`

## Technologies Used
- **Laravel**: Robust PHP framework for backend development.
- **Vue.js**: Dynamic JavaScript framework for frontend UI.
- **API**: Connects the frontend and backend for data exchange.

## Database Setup
- Create a MySQL database.
- Update `.env` with database credentials.
- Run database migrations: `php artisan migrate`

## Running the Application
- Compile frontend assets: `npm run dev` or `npm run prod` for production.
- Start the development server: `php artisan serve`
- Access the application in your browser at `http://127.0.0.1:8000`

## Usage
- Use the application to perform CRUD operations on your data.
- Navigate through different sections such as Create, Read, Update, and Delete to manage your resources.

## API Endpoints
- API endpoints are located in `routes/api.php`.
- Test API endpoints using tools like Postman or Insomnia.

## Contributing
Contributions are welcome! Fork the repository and create pull requests with your changes.

## License
This project is licensed under the [MIT License](LICENSE).
