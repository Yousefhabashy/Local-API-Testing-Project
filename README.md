# 🧪 API Testing Project – Postman & Newman

This project demonstrates **API Testing** using **Postman** and **Newman CLI**.  
It focuses on testing an **E-commerce API**, covering authentication, users, products, and orders endpoints.

---

## 🚀 Project Overview

The goal of this project is to **automate API testing** and ensure that all endpoints work as expected.  
The tests validate responses, check performance, and handle dynamic data like authentication tokens.

---

## ⚙️ Tools & Technologies

- 🧰 **Postman** – Create, manage, and test APIs visually  
- ⚡ **Newman** – Run Postman collections from the command line  
- 💡 **JavaScript** – Used for writing custom test scripts  
- 📂 **JSON** – For storing environment variables and data  

---

## 📁 Project Structure

Local-API-Testing-Project/
├── ADMIN Collection.postman_collection.json   
├── USER Collection.postman_collection.json  
├── Local.postman_environment.json  
└── README.md  

## 🧠 Key Features

- ✅ Automated testing for multiple endpoints  
- 🔑 Dynamic token extraction and environment variable handling  
- 🧩 Organized Postman environment setup  
- ⚙️ Validation of response codes and body data  
- ⚡ Response time performance checks  
- 🧾 Easy integration with CI/CD pipelines  

---

## 🧰 Example Test Script

```javascript
var responseBody = pm.response.json();

let adminToken = responseBody.accessToken;
pm.environment.set("adminToken", adminToken);

pm.test("Token is set in environment", function () {
    pm.expect(adminToken).to.not.be.null;
});

pm.test("Successful Admin Login", function () {
    pm.response.to.have.status(200);
});

pm.test("Response time", function () {
    pm.expect(pm.response.responseTime).to.be.below(200);
});
```
How to Run Tests

Install Node.js
Download and install from nodejs.org

Install Newman

```npm install -g newman```


Run the Collection

```newman run "Admin Collection.postman_collection.json" -e "environment.json" -r cli,html```


(Optional) – Export the report in HTML format:

```newman run "Admin Collection.postman_collection.json" -e "environment.json" -r html```

📊 Test Results & Reporting

Newman provides:

🧾 CLI reports (terminal output)

🌐 HTML reports (for documentation)

🧪 JSON/JUnit reports (for CI tools)

These reports show request success/failure, response times, and test coverage.
💡 Notes

Make sure your local server is running (e.g., http://localhost:3000)

Update base_url in environment.json before running tests

You can modify or extend the collection directly from Postman
👨‍💻 Author

Yousef Ahmed Mohamed Habashy
Software Testing Trainee @ DEPI
🎓 Faculty of Science, Menoufia University

📧 yousefgriezmann58@gmail.com
