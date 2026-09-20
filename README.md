# Patient Management API

A FastAPI-based patient management system with CRUD operations, Pydantic data validation, and automatically computed BMI/verdict fields.

## Features

- Create, view, update, and delete patient records
- Automatic BMI calculation and health verdict (Underweight / Normal / Obese) via Pydantic computed fields
- Sort patients by height, weight, or BMI (ascending/descending)
- Input validation using Pydantic (age, height, weight, gender constraints)
- JSON file-based storage

## Tech Stack

- **FastAPI** – web framework
- **Pydantic** – data validation and computed fields
- **Python 3**

## Getting Started

### Prerequisites
- Python 3.8+
- pip

### Installation

```bash
pip install fastapi uvicorn
```

### Running the API

```bash
uvicorn main:app --reload
```

The API will be available at `http://127.0.0.1:8000`
Interactive docs (Swagger UI) at `http://127.0.0.1:8000/docs`

## API Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/` | Welcome message |
| GET | `/about` | About the API |
| GET | `/view` | View all patients |
| GET | `/patient/{patient_id}` | View a specific patient by ID |
| GET | `/sort?sort_by=&order=` | Sort patients by height, weight, or bmi |
| POST | `/create` | Add a new patient |
| PUT | `/edit/{patient_id}` | Update an existing patient |
| DELETE | `/delete/{patient_id}` | Delete a patient |

## Example: Create a Patient

```json
POST /create
{
  "id": "P001",
  "name": "Hritik Roshan",
  "city": "Hyderabad",
  "age": 30,
  "gender": "Male",
  "height": 1.75,
  "weight": 70
}
```

Response includes computed `bmi` and `verdict` fields automatically.

## Data Storage

Patient records are stored in a local `patients.json` file (not included in this repo — create an empty `{}` file named `patients.json` in the project root before running).

## License

This project is for learning/portfolio purposes.