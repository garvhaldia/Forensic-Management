# Forensic Management System

A comprehensive forensic database management system built with Python, Streamlit, and MySQL. This application provides an intuitive interface for managing forensic cases, evidence, criminals, and various types of forensic data including ballistics, drugs, paint analysis, and automobile evidence.

## 📋 Table of Contents
- [Features](#features)
- [Technologies Used](#technologies-used)
- [Project Structure](#project-structure)
- [Database Schema](#database-schema)
- [Installation](#installation)
- [Usage](#usage)
- [Authentication](#authentication)
- [Screenshots](#screenshots)
- [Contributing](#contributing)


## ✨ Features

### Core Functionality
- **Case Management**: Create, view, update, and delete forensic cases
- **Criminal Records**: Manage criminal profiles with DNA and fingerprint data
- **Evidence Management**: Handle multiple types of evidence:
  - Ballistics (firearms, ammunition)
  - Drug analysis
  - Paint samples
  - Automobile evidence
- **Advanced Queries**: Pre-defined forensic queries for data analysis
- **Custom SQL Commands**: Execute custom database queries
- **User Authentication**: Secure login system with hashed passwords

### User Interface
- Interactive web-based interface using Streamlit
- Custom styling with forensic-themed backgrounds
- Responsive sidebar navigation
- Data visualization with pandas DataFrames

## 🛠 Technologies Used

- **Backend**: Python 3.9+
- **Frontend**: Streamlit
- **Database**: MySQL
- **Authentication**: Streamlit-Authenticator
- **Data Processing**: Pandas
- **Styling**: Custom CSS with Streamlit

## 📁 Project Structure

```
ForensicManagement/
├── Python/
│   ├── app.py                 # Main application entry point
│   ├── auth.py               # Authentication module (basic version)
│   ├── auth1.py              # Enhanced authentication module
│   ├── database.py           # Database connection and operations
│   ├── add.py                # Add records functionality
│   ├── add2.py               # Enhanced add records functionality
│   ├── read.py               # View/read records functionality
│   ├── update.py             # Update records (basic version)
│   ├── update1.py            # Enhanced update functionality
│   ├── delete.py             # Delete records functionality
│   ├── queries.py            # Predefined queries and custom SQL
│   ├── test.py               # Utility functions for ID generation
│   ├── hashed_pw.pkl         # Encrypted password storage
│   └── config.yaml           # Configuration file
├── Queries/
│   └── Create.sql            # Database schema creation script
├── Forensics_331.sql         # Complete database dump
├── ER Diagram.png            # Entity-Relationship diagram
├── imagebackground.jpg       # Background image for UI
├── Update in cmd.txt         # Update instructions
└── README.md                 # Project documentation
```

## 🗄 Database Schema

The system manages the following entities:

- **CASES**: Forensic case information
- **CRIMINAL**: Criminal records with biometric data
- **BALLISTICS**: Firearm and ammunition evidence
- **DRUGS**: Drug-related evidence and analysis
- **PAINT**: Paint sample analysis
- **AUTOMOBILE**: Vehicle-related evidence
- **CRIMINALCASE**: Linking table for criminals and cases

View the complete schema in [`Queries/Create.sql`](Queries/Create.sql) and the ER diagram in [`ER Diagram.png`](ER%20Diagram.png).

## 🚀 Installation

### Prerequisites
- Python 3.9 or higher
- MySQL Server
- Git

### Step 1: Clone the Repository
```bash
git clone https://github.com/yourusername/ForensicManagement.git
cd ForensicManagement
```

### Step 2: Install Dependencies
```bash
pip install streamlit
pip install mysql-connector-python
pip install pandas
pip install streamlit-authenticator
pip install plotly-express
```

### Step 3: Database Setup
1. Install and start MySQL Server
2. Create a new database:
   ```sql
   CREATE DATABASE forensics_db;
   ```
3. Import the database schema:
   ```bash
   mysql -u your_username -p forensics_db < Forensics_331.sql
   ```

### Step 4: Configure Database Connection
Update the database connection parameters in [`Python/database.py`](Python/database.py):
```python
connection = mysql.connector.connect(
    host='localhost',
    user='your_username',
    password='your_password',
    database='forensics_db'
)
```

## 💻 Usage

### Running the Application

#### With Authentication (Recommended)
```bash
cd Python
streamlit run auth1.py
```

#### Without Authentication (Development)
```bash
cd Python
streamlit run app.py
```

### Default Login Credentials
- **Username**: Bhuvan or chandan
- **Password**: (Contact administrator for credentials)

### Main Features

1. **Add Records**: Create new cases, criminals, and evidence entries
2. **View Tables**: Browse and search through all database records
3. **Update Records**: Modify existing entries with validation
4. **Delete Records**: Remove records with confirmation
5. **Predefined Queries**: Run common forensic analysis queries
6. **Custom Commands**: Execute custom SQL queries for advanced analysis

## 🔐 Authentication

The system uses streamlit-authenticator for secure user management:

- Passwords are hashed and stored securely
- Session management with configurable expiry
- Logout functionality
- Multiple user support

To add new users, update the credentials in [`Python/auth1.py`](Python/auth1.py) and regenerate the password hash file.

## 📸 Screenshots

The application features:
- Custom forensic-themed background
- Professional sidebar navigation
- Interactive data tables
- Form-based data entry
- Real-time data updates

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

### Development Guidelines
- Follow Python PEP 8 style guidelines
- Add comments for complex functions
- Test all database operations
- Ensure security best practices


## 🆘 Support

For support and questions:
1. Check the existing issues in the repository
2. Create a new issue with detailed description
3. Contact the development team

## 🔄 Version History

- **v1.0** - Initial release with core functionality
- **v1.1** - Enhanced authentication and UI improvements
- **v1.2** - Added advanced query features and better error handling

---

**Note**: This is an educational project for database management and forensic data handling. Ensure compliance with local laws and regulations when handling actual forensic data.
