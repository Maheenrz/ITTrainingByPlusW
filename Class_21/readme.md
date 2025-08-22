## 📡 Class 21 – API Testing with Postman

### What I did

I created **4 APIs (GET, POST, PUT, DELETE)** in my Django `posts` app and tested them in Postman.

### 🔹 API Endpoints

* **GET** → `http://127.0.0.1:8000/api/get/`
* **POST** → `http://127.0.0.1:8000/api/post/?name=Ali`
* **PUT** → `http://127.0.0.1:8000/api/put/`
* **DELETE** → `http://127.0.0.1:8000/api/delete/`

### 🔹 Example Postman Tests

1. **GET**

   * Method: `GET`
   * URL: `http://127.0.0.1:8000/api/get/`
   * Response:

     ```json
     { "message": "This is GET request" }
     ```

2. **POST**

   * Method: `POST`
   * URL: `http://127.0.0.1:8000/api/post/?name=Ali`
   * Response:

     ```json
     { "message": "This is POST request, name=Ali" }
     ```

3. **PUT**

   * Method: `PUT`
   * URL: `http://127.0.0.1:8000/api/put/`
   * Response:

     ```json
     { "message": "This is PUT request" }
     ```

4. **DELETE**

   * Method: `DELETE`
   * URL: `http://127.0.0.1:8000/api/delete/`
   * Response:

     ```json
     { "message": "This is DELETE request" }
     ```

---

## 📌 Submission

* ✅ Uploaded code on GitHub
* ✅ Added this documentation
* ✅ Will post LinkedIn update tagging instructors

---