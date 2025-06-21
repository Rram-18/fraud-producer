# Fraud Transaction Producer

This Spring Boot microservice simulates user transactions and publishes them to a Kafka topic named `transactions`.

## Features
- REST API to send transaction data
- Kafka producer integration
- Simple transaction model with id, user, amount, location, timestamp, and IP address

## How to Run
1. Start Kafka and Zookeeper locally.
2. Run this Spring Boot application.
3. Use Postman or any HTTP client to send POST requests to `/api/transactions`.

## Example Request

```json
{
  "transactionId": "TXN1001",
  "userId": "user123",
  "amount": 1000,
  "location": "Delhi",
  "timestamp": "2025-06-21T22:00:00",
  "ipAddress": "192.168.1.2"
}
Technology Stack
Java 17+

Spring Boot

Apache Kafka

Maven

yaml
Copy
Edit

7. Save the file (Ctrl + S or File → Save).

---

## For **fraud-receiver** project:

1. Open **fraud-receiver** project in IntelliJ.

2. Find the root folder of this project in the **Project** pane.

3. Right-click on the root folder.

4. Select **New** → **File**

5. Name the file exactly:  
   `README.md`

6. Paste the following receiver README content inside:

```markdown
# Fraud Detection & Alert Receiver

This Spring Boot microservice listens to Kafka's `transactions` topic and performs fraud detection based on transaction amount and IP location.

## Features
- Kafka consumer listens to `transactions`
- Fraud detection rules:
  - Transaction amount above configured threshold (₹50,000)
  - IP address from outside India
- Stores fraud alerts in MySQL database
- Sends email alerts for fraudulent transactions

## How to Run
1. Make sure Kafka, Zookeeper, and MySQL are running.
2. Run this Spring Boot application.
3. Check fraud alerts via REST API `/api/fraud-alerts`.
4. Monitor email inbox for fraud alert notifications.

## Technology Stack
- Java 17+
- Spring Boot
- Apache Kafka
- MySQL
- SMTP Email (Gmail)
- Maven