# MERN Stack Developer Assessment

## Overview
This project is part of the Roxiler campus recruitment process. The goal is to create a MERN Stack application that includes backend APIs and a frontend interface to manage, display, and analyze transaction data fetched from a third-party API. 

## Task Description
The project is divided into two main parts:

1. **Backend**
   - Fetch data from a third-party API and initialize the database.
   - Create APIs to support various operations such as listing transactions, generating statistics, and creating visualizations.

2. **Frontend**
   - Use the created APIs to display a table of transactions and charts (bar and pie charts) on a single-page application.

## Features

### Backend Features

1. **Initialize Database**
   - Fetch data from the third-party API.
   - URL: `https://s3.amazonaws.com/roxiler.com/product_transaction.json`
   - Method: `GET`
   - Store the data in the database with an efficient table/collection structure.

2. **APIs**

   - **List Transactions**:
     - Supports search and pagination on product transactions.
     - Search by `title`, `description`, or `price`.
     - Pagination with default values `page = 1` and `per page = 10`.

   - **Statistics API**:
     - Total sale amount for a selected month.
     - Total number of sold items for the selected month.
     - Total number of unsold items for the selected month.

   - **Bar Chart API**:
     - Provides the number of items within predefined price ranges for the selected month:
       - 0-100, 101-200, ..., 901 and above.

   - **Pie Chart API**:
     - Finds unique categories and the number of items in each category for the selected month.

   - **Combined API**:
     - Fetches data from the above APIs, combines their responses, and returns a consolidated JSON.

### Frontend Features

1. **Transaction Table**:
   - Displays transactions for a selected month (default: March).
   - Supports search functionality to filter transactions by `title`, `description`, or `price`.
   - Supports pagination (Next/Previous buttons).

2. **Transaction Statistics**:
   - Displays total sale amount, total sold items, and total unsold items for the selected month.

3. **Bar Chart**:
   - Displays the number of items within predefined price ranges for the selected month.

4. **Pie Chart**:
   - Displays unique categories and the number of items in each category for the selected month.

## Installation and Setup

### Prerequisites
- Node.js
- MongoDB
- Git

### Steps to Run

1. Clone the repository:
   ```bash
   git clone <repository_url>
   cd <repository_folder>
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Set up the `.env` file with the following variables:
   ```env
   MONGO_URI=<your_mongodb_connection_string>
   PORT=<port_number>
   ```

4. Run the backend server:
   ```bash
   npm start
   ```

5. Navigate to the frontend folder and install dependencies:
   ```bash
   cd frontend
   npm install
   ```

6. Run the frontend application:
   ```bash
   npm start
   ```

7. Access the application in your browser:
   ```
   http://localhost:<frontend_port>
   ```

## APIs Documentation

1. **Initialize Database**
   - URL: `/api/initialize`
   - Method: `GET`

2. **List Transactions**
   - URL: `/api/transactions`
   - Method: `GET`
   - Query Parameters:
     - `search` (optional)
     - `page` (optional)
     - `perPage` (optional)

3. **Statistics API**
   - URL: `/api/statistics`
   - Method: `GET`
   - Query Parameters:
     - `month` (required)

4. **Bar Chart API**
   - URL: `/api/bar-chart`
   - Method: `GET`
   - Query Parameters:
     - `month` (required)

5. **Pie Chart API**
   - URL: `/api/pie-chart`
   - Method: `GET`
   - Query Parameters:
     - `month` (required)

6. **Combined API**
   - URL: `/api/combined`
   - Method: `GET`
   - Query Parameters:
     - `month` (required)

## Technologies Used

### Backend
- Node.js
- Express.js
- MongoDB

### Frontend
- React.js
- Redux
- Chart.js

## Project Structure
```
|-- backend
|   |-- models
|   |-- routes
|   |-- controllers
|-- frontend
|   |-- components
|   |-- pages
|   |-- services
```

## Author
Rajesh Kumar

## Notes
- Ensure your MongoDB service is running locally or provide a valid connection string.
- Use Postman or a similar tool to test the APIs if needed.

## License
This project is created for the Roxiler assessment and is not licensed for commercial use.
