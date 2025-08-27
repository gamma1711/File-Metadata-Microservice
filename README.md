# File Metadata Microservice

A simple REST API built with **Node.js**, **Express**, and **Multer** to upload files and retrieve their metadata.  
The API returns the original filename, MIME type, and size in bytes of the uploaded file.

---

## Table of Contents

- [Description](#description)
- [Installation](#installation)
- [Usage](#usage)
- [Endpoints](#endpoints)
- [File Upload Form](#file-upload-form)
- [Response](#response)
- [Error Handling](#error-handling)
- [Technologies](#technologies)

---

## Description

This project allows users to upload a file through a POST request.  
Instead of saving the file permanently, it is stored in memory, and the API responds with a JSON object containing:

- `name` → original name of the file
- `type` → MIME type of the file
- `size` → file size in bytes

This microservice is ideal for learning how to handle file uploads in Node.js without storing files on disk.

---

## Installation

1. Clone the repository:

```
git clone <repo_url>
cd <project_folder>
```
2. Install dependencies:
```
npm install
```
3. Create a .env file (optional) to define PORT.

4. Start the server:
```
npm start
```
The server will run on http://localhost:3000 by default.
---
## Usage
### Endpoint
```
POST /api/fileanalyse
```
Accepts a single file with the field name upfile.

### File Upload Form
You can use the HTML form at the root / to upload files:
```
<form action="/api/fileanalyse" method="post" enctype="multipart/form-data">
  <input type="file" name="upfile" />
  <input type="submit" value="Upload" />
</form>
```
### Request
Method: POST

Content-Type: multipart/form-data

Field name: upfile

Response
If the file is successfully uploaded, you receive a JSON object:
```
{
  "name": "example.png",
  "type": "image/png",
  "size": 12345
}

```
name: Original file name

type: MIME type

size: Size in bytes
---
## Technologies
- Node.js

- Express.js

- Multer

- CORS

---
## Notes
The uploaded files are not saved to disk; they are stored temporarily in memory.

This microservice is ideal for learning file uploads and metadata extraction.

You can extend it to store files, validate types, or upload to cloud storage.

