# Python-s3-assignmnet

AWS S3 File Uploader (FastAPI)

A FastAPI application to manage AWS S3 buckets, folders, and files using REST APIs.

Tech Stack

Python 3.10+

FastAPI

boto3 (AWS SDK)

Uvicorn

python-dotenv

 Features
Health check

List / create / delete S3 buckets

Create / delete folders

Upload & delete files

Copy & move files within S3

Swagger UI support

 Setup & Run
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt


Set AWS credentials:

AWS_ACCESS_KEY_ID=YOUR_KEY
AWS_SECRET_ACCESS_KEY=YOUR_SECRET
AWS_REGION=ap-south-2


Run the app:

uvicorn app.main:app --reload


Open API docs:
👉 http://localhost:8000/docs

 Health Check

GET /ping

{ "status": "alive" }

📌 S3 APIs (/s3)

GET /s3/buckets – List buckets

POST /s3/create-bucket – Create bucket

DELETE /s3/bucket/{bucket_name} – Delete bucket

POST /s3/create-folder – Create folder

DELETE /s3/delete-folder – Delete folder

POST /s3/upload-file/{bucket_name} – Upload file

DELETE /s3/delete-file/{bucket_name} – Delete file

POST /s3/copy-file – Copy file

POST /s3/move-file – Move file

🏗 Project Structure
app/
├── main.py
├── core/config.py
├── health_check/ping.py
└── s3_bucket/
    ├── routes/
    ├── services/
    ├── repositories/
    └── schemas/

Notes

Uses AWS credentials via environment variables

Do not commit credentials to source control

Folders are implemented as S3 prefixes (/)
