# DiceBank

DiceBank is a modern banking API built with [FastAPI](https://fastapi.tiangolo.com/), allowing users to securely manage accounts, handle transactions, and view financial history. Designed for reliability, security, and scalability, DiceBank is ideal for education, prototyping, and small production deployments.

---

## Features

- User registration & authentication
- Account creation and management
- Deposit, withdrawal, and transfer functionality
- Transaction history tracking
- Secure password handling and input validation
- Admin operations (optional)

---

## Technology Stack

- **Backend:** FastAPI (Python)
- **Database:** SQL (e.g., SQLite, PostgreSQL)
- **ORM:** SQLAlchemy or Tortoise ORM
- **Authentication:** JWT or OAuth2
- **Documentation:** Automatic Swagger UI (/docs)

---

## Getting Started

### Installation

1. Clone the repository:
   ```sh
   git clone https://github.com/Slatyy26/DiceBank.git
   cd DiceBank
   ```
2. *(Optional but recommended)* Create a virtual environment:
   ```sh
   python -m venv venv
   source venv/bin/activate     # On Windows: venv\Scripts\activate
   ```
3. Install dependencies:
   ```sh
   pip install -r requirements.txt
   ```

### Running the Application

```sh
uvicorn main:app --reload
```

- Access interactive API docs at: [http://127.0.0.1:8000/docs](http://127.0.0.1:8000/docs)

---

## Example Endpoints

| Method | Endpoint         | Description                    |
|--------|------------------|--------------------------------|
| POST   | /register        | User registration              |
| POST   | /login           | User login                     |
| POST   | /deposit         | Deposit money into account     |
| POST   | /withdraw        | Withdraw money from account    |
| POST   | /transfer        | Transfer funds between accounts|
| GET    | /balance         | Retrieve account balance       |
| GET    | /transactions    | View transaction history       |
| GET    | /admin/users     | Admin: list all users          |

---

### Sample API Usage

#### Register a User
```http
POST /register
{
  "username": "alice",
  "email": "alice@example.com",
  "password": "StrongPassword123"
}
```

#### Deposit Funds
```http
POST /deposit
{
  "user_id": 1,
  "amount": 100.00
}
```

---

## Example Database Schema

**Users**
- id (int)
- username (str)
- email (str)
- hashed_password (str)

**Accounts**
- id (int)
- user_id (int)
- balance (float)

**Transactions**
- id (int)
- account_id (int)
- type (str): deposit, withdrawal, transfer
- amount (float)
- timestamp (datetime)

---

## Contributing

Pull requests are welcome!  
1. Fork the repository  
2. Create a feature branch  
3. Make your changes  
4. Push branch and open a PR

---

## License

MIT License

---

**Created by [Slatyy26](https://github.com/Slatyy26)**
