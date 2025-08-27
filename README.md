# 🧾 Actual Budget API Wrapper

![Python Version](https://img.shields.io/badge/python-3.10+-blue.svg)
![License](https://img.shields.io/badge/license-MIT-green.svg)
![FastAPI](https://img.shields.io/badge/FastAPI-API-green)

A simple FastAPI-based wrapper that allows you to interact with [Actual Budget](https://actualbudget.org/) — a powerful local-first budgeting tool — via a minimal HTTP API.

Since Actual Budget does not provide an official REST API, this project serves as a thin layer to enable **automated creation of transactions**, using the [actualpy](https://github.com/bvanelli/actualpy) module under the hood.

⚠️ NOTE: this project is very simple, but it's in very early development.

## ✨ Features

- 🔐 Secured with API Key authentication
- 🔁 Add new transactions via a single HTTP endpoint
- ⚙️ Docker-ready deployment
- 🧩 Easy integration with your automation scripts or external services

## 🛠️ Setup

Create a `.env` file with the following variables:

```env
API_KEY=your_super_secret_key
ACTUAL_HOST=http://actual-host:5006
ACTUAL_PASSWORD=your_password
ACTUAL_FILE=your_budget_name
```

- `API_KEY`: Key required to authorize API requests.
- `ACTUAL_HOST`: URL to your Actual Budget instance.
- `ACTUAL_PASSWORD`: Password for the Actual Budget.
- `ACTUAL_FILE`: Budget file name to use.

## 🚀 Usage

### 🐳 Using Docker (recommended)

```bash
docker compose up --build
```

### 🧪 Local install (Python 3.10+)

```bash
pip install -r requirements.txt
uvicorn main:app --reload
```

## 🧠 API Reference

### `POST /transaction`

Adds a new transaction to your Actual Budget file.

**Headers:**

```
x-api-key: your_super_secret_key
Content-Type: application/json
```

**Request body:**

```json
{
  "amount": 12.99,
  "payee": "Spotify",
  "account": "checking",
  "notes": "Monthly plan",
  "outcome": true
}
```

## 📦 Dependencies

- [FastAPI](https://fastapi.tiangolo.com/)
- [actualpy](https://github.com/bvanelli/actualpy)
- [python-dotenv](https://pypi.org/project/python-dotenv/)

## 📄 License

This project is licensed under the MIT License.
