# Rule Engine Application
Hosted link: https://github.com/yashasvi129/Rule-Engine-with-AST/tree/master

## Overview

This application is a rule engine that determines user eligibility based on attributes such as age, department, salary, and experience. It uses an Abstract Syntax Tree (AST) to represent and manage conditional rules, allowing for dynamic rule creation, combination, and evaluation.

<img width="705" alt="image" src="https://github.com/user-attachments/assets/59a815a6-3fd7-4eb3-bbec-e7b6a62b4104">




## Features

- **Create Rules:** Define rules using a string format that gets converted into an AST.
  
 <img width="504" alt="image" src="https://github.com/user-attachments/assets/a77e4cb8-6c3b-4d5a-bddd-cbede0a0666c">



- **Combine Rules:** Combine multiple rules into a single AST for more complex evaluations.
  
  <img width="657" alt="image" src="https://github.com/user-attachments/assets/6e9f02a7-66ba-4b9c-82ef-f34f1c0274e6">


  
- **Evaluate Rules:** Check if the given data meets the criteria defined by the AST.
  
  <img width="501" alt="image" src="https://github.com/user-attachments/assets/702888e0-704c-41f5-9894-121965d2468f">

<img width="729" alt="image" src="https://github.com/user-attachments/assets/8f836c4b-61d1-4673-87ca-42b835499a6b">


- **Tree Visualization:** Define or Combine Rule would should show Tree Representation.

## Tech Stack

- **Backend:** Node.js, Express.js
- **Database:** MongoDB

## Getting Started

### Prerequisites

- Node.js and npm installed
- MongoDB installed and running

### Installation

1. **Clone the Repository**
   ```bash
   git clone "https://github.com/yashasvi129/Rule-Engine-with-AST.git"
   cd rule-engine
   ```

2. **Install Backend Dependencies**

   ```bash
   npm install
   ```
   
3. **Start MongoDB**

   Ensure that MongoDB is running on your local machine:

   ```bash
   mongod
   ```

4. **Start the Backend Server**

   ```bash
   nodemon server.js
   ```

## API Endpoints

1. **Create a Rule**
   - **Endpoint:** `/api/create_rule`
   - **Method:** POST
   - **Body:**

     ```json
     {
       "ruleString": "((age > 30 AND department = 'Sales') OR (age < 25 AND department = 'Marketing')) AND (salary > 50000 OR experience > 5)",
       "ruleName": "Rule 1"
     }
     ```
use appropriate spaces in Rules for correct results.

Rule should be in follow format:
variable operator value 

   - **Response:**

     ```json
     {
       "_id": "605c72ef1f4e3a001f4d2e9a",
       "rule_name": "Rule1",
       "rule_ast": { ... }
     }
     ```

2. **Combine Rules**
   - **Endpoint:** `/api/rules/combine_rules`
   - **Method:** POST
   - **Body:**

     ```json
     {
       "ruleIds": ["605c72ef1f4e3a001f4d2e9a", "605c730f1f4e3a001f4d2e9b"]
       "operators: op
     }
     ```
   - **Response:**

     ```json
     {
       "type": "operator",
       "value": operator,
       "left": { ... },
       "right": { ... }
     }
     ```

3. **Evaluate a Rule**
   - **Endpoint:** `/api/rules/evaluate_rule`
   - **Method:** POST
   - **Body:**

     ```json
     {
       "rule": { ... },
       "data": {
         "age": 35,
         "department": "Sales",
         "salary": 60000,
         "experience": 3
       }
     }
     ```
   - **Response:**

     ```json
     {
       "result": true
     }
     ```

## Running Tests

You can add and run tests to ensure everything is working correctly. 
```
created by: yashasvi garg
