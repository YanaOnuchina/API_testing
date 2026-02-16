# Trello API Automation Project (Postman + Newman)
Automating critical scenarios for working with Trello boards and cards
## **Tech stack:** Postman, Newman, JavaScript, Chai.js

## **How to Run:**
1) Install Newman: npm install -g newman
2) Clon the repository
3) Put your trello key and trello token to environments/trello_env.json
4) Run command: newman run collections/trello_tests.json -e environments/trello_env.json

## **Structure:**
#### Positive Scenarios (End-to-End Flow)
    - Board Lifecycle: Successful creation of a new board with dynamic naming and its subsequent deletion.
    - List Management: Creation of multiple lists linked to the specific board ID.
    - Card Operations: Creation of a new card within a specific list.
    - Card Movement: Updating the card's position or moving it between lists using PUT requests.

#### Integration & Data Integrity
    - Dynamic Variable Chaining: Passing variables (Board ID, List ID, Card ID) between sequential requests.
    - JSON Schema Validation: Verifying that the API response structure matches the expected data types and mandatory fields.
    - Response Benchmarking: Ensuring critical endpoints respond within a defined threshold (e.g., < 600ms).

#### Negative & Security Testing
    - Unauthorized Access: Verifying that requests without a valid API Key or Token return a 401 Unauthorized status.
    - Invalid Resource Referencing: Attempting to create or fetch items using non-existent IDs (404 Not Found).
    - Data Validation: Testing API resilience when sending empty mandatory fields.

#### **Results**
Screenshot from Postman:
<img width="900" height="600" alt="image" src="https://github.com/user-attachments/assets/36508804-234c-41ed-9600-5a9f060a8e32" />

Newman report screenshot:
<img width="900" height="600" alt="image" src="https://github.com/user-attachments/assets/78ab7f05-ec62-49d9-b58c-fc259ed30b89" />

