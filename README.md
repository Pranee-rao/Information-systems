# CMU Merrill Dining Dashboard

This Streamlit application serves as a dashboard for managing employee data at CMU Merrill Dining. It includes functionalities such as viewing employee data, adding new entries, and deleting existing entries from a MySQL database.

## Features

- **Home Page**: Welcome page with information about CMU Merrill Dining.
- **Login**: Secure login functionality for managers.
- **Dashboard**: Displays a table of current employee data.
- **Add Employee**: Form to add new employee entries.
- **Delete Employee**: Form to delete existing employee entries.

## Setup Instructions

### Prerequisites

- Python 3.x
- Streamlit
- MySQL Connector for Python
- Pandas

### Installation

1. Clone the repository:
    ```sh
    git clone https://github.com/pranee_rao/information-systems.git
    ```

2. Navigate to the project directory:
    ```sh
    cd information-systems
    ```

3. Install the required packages:
    ```sh
    pip install streamlit mysql-connector-python pandas
    ```

### Database Setup

```sql
CREATE TABLE Employee (
    EmployeeID INT PRIMARY KEY,
    FirstName VARCHAR(50),
    LastName VARCHAR(50),
    HireDate DATE
);
def connect_to_database():
    try:
        conn = mysql.connector.connect(
            host="your_host",
            user="your_username",
            password="your_password",
            database="your_database"
        )
        return conn
    except mysql.connector.Error as e:
        st.error(f"Error connecting to the database: {e}")
        return None
streamlit run app.py
