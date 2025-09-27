---
title: Hyfn API Documentation
fullscreen: false
hidden: true
---
This document provides detailed information about the Hyfn API, including endpoints, request methods, headers, and example payloads. The API is organized into several collections: Agents, Jobs, JobTasks, JobLogs, and AgentLogs. Each section below describes the available endpoints, their purpose, and how to interact with them.

```text
# Hyfn API Documentation

This document provides detailed information about the **Hyfn API**, including endpoints, request methods, headers, and example payloads.  

The API is organized into the following collections:
- **Agents**
- **Jobs**
- **JobTasks**
- **JobLogs**
- **AgentLogs**


## Base URL

All API requests should be made to the following base URL:

```

[https://eaf2221b-446d-4907-8f99-314e441b38c3-00-2ndzo2ggoue2h.kirk.replit.dev/api](https://eaf2221b-446d-4907-8f99-314e441b38c3-00-2ndzo2ggoue2h.kirk.replit.dev/api)

```

---

## Authentication

All endpoints require an **X-Agent-Key** header for authentication.  
The key must be included in every request as follows:

- **Header Name**: `X-Agent-Key`  
- **Value**: `sk-OlvThjkMzIZ5623mA5duuUs5k9pBsFUO2MbtEy7gYIA`

Additionally, all requests must include:

```

Content-Type: application/json

```

---

## Endpoints

### 1. Agents

#### Invoke Agent

Invokes an agent with a specific message.

- **Endpoint**: `/agents/{agentId}/invoke`  
- **Method**: `POST`  
- **Description**: Sends a message to a specific agent identified by `agentId` to invoke an action or process.  
- **Example URL**:  
```

[https://.../api/agents/j9716pwawqtkjpnsf8n9t0nhc97qp7p9/invoke](https://.../api/agents/j9716pwawqtkjpnsf8n9t0nhc97qp7p9/invoke)

````

**Headers**
```json
{
"X-Agent-Key": "sk-OlvThjkMzIZ5623mA5duuUs5k9pBsFUO2MbtEy7gYIA",
"Content-Type": "application/json"
}
````

**Request Body**

```json
{
  "message": "who are you?"
}
```

**Example cURL**

```bash
curl -X POST "https://.../api/agents/j9716pwawqtkjpnsf8n9t0nhc97qp7p9/invoke" \
-H "X-Agent-Key: sk-OlvThjkMzIZ5623mA5duuUs5k9pBsFUO2MbtEy7gYIA" \
-H "Content-Type: application/json" \
-d '{"message": "who are you?"}'
```

***

### 2. Jobs

#### Get All Jobs

Retrieves a list of all jobs.

* **Endpoint**: `/jobs`
* **Method**: `GET`
* **Description**: Fetches all available jobs in the system.
* **Example URL**:

  ```
  https://.../api/jobs
  ```

**Headers**

```json
{
  "X-Agent-Key": "sk-OlvThjkMzIZ5623mA5duuUs5k9pBsFUO2MbtEy7gYIA",
  "Content-Type": "application/json"
}
```

**Request Body**: `None`

**Example cURL**

```bash
curl -X GET "https://.../api/jobs" \
-H "X-Agent-Key: sk-OlvThjkMzIZ5623mA5duuUs5k9pBsFUO2MbtEy7gYIA" \
-H "Content-Type: application/json"
```

***

### 3. JobTasks

#### Get All Job Tasks

Retrieves all tasks associated with a specific job.

* **Endpoint**: `/jobs/{jobId}/jobTasks`
* **Method**: `GET`
* **Description**: Fetches all tasks for a job identified by `jobId`.
* **Example URL**:

  ```
  https://.../api/jobs/k17ewwr3aewr98c87pkf3w633d7qjvc2/jobTasks
  ```

**Headers**

```json
{
  "X-Agent-Key": "sk-OlvThjkMzIZ5623mA5duuUs5k9pBsFUO2MbtEy7gYIA",
  "Content-Type": "application/json"
}
```

**Request Body**: `None`

**Example cURL**

```bash
curl -X GET "https://.../api/jobs/k17ewwr3aewr98c87pkf3w633d7qjvc2/jobTasks" \
-H "X-Agent-Key: sk-OlvThjkMzIZ5623mA5duuUs5k9pBsFUO2MbtEy7gYIA" \
-H "Content-Type: application/json"
```

***

### 4. JobLogs

#### Get All Job Logs

* **Endpoint**: `/jobLogs`
* **Method**: `GET`
* **Description**: Fetches all job logs in the system.
* **Example URL**:

  ```
  https://.../api/jobLogs
  ```

**Example cURL**

```bash
curl -X GET "https://.../api/jobLogs" \
-H "X-Agent-Key: sk-OlvThjkMzIZ5623mA5duuUs5k9pBsFUO2MbtEy7gYIA" \
-H "Content-Type: application/json"
```

***

#### Create Log Item

* **Endpoint**: `/jobLogs`
* **Method**: `POST`
* **Description**: Creates a new log entry for a job.

**Request Body**

```json
{
  "jobId": "k170hbfq9mfv85p59x4qrp6a957qkn0p",
  "input": "{}",
  "output": "{}",
  "status": "started",
  "timeSpent": 0,
  "startedAt": "2025-09-20T12:34:56Z"
}
```

**Example cURL**

```bash
curl -X POST "https://.../api/jobLogs" \
-H "X-Agent-Key: sk-OlvThjkMzIZ5623mA5duuUs5k9pBsFUO2MbtEy7gYIA" \
-H "Content-Type: application/json" \
-d '{"jobId":"k170hbfq9mfv85p59x4qrp6a957qkn0p","input":"{}","output":"{}","status":"started","timeSpent":0,"startedAt":"2025-09-20T12:34:56Z"}'
```

***

#### Update Log Item

* **Endpoint**: `/jobLogs/{logId}`
* **Method**: `PUT`
* **Description**: Updates a job log entry identified by `logId`.

**Request Body**

```json
{
  "jobId": "k170hbfq9mfv85p59x4qrp6a957qkn0p",
  "input": "{}",
  "output": "{}",
  "status": "completed",
  "timeSpent": 1200,
  "startedAt": "2025-09-20T12:34:56Z"
}
```

**Example cURL**

```bash
curl -X PUT "https://.../api/jobLogs/js73gfsq9rt219k58vqdnx0g4d7qrfrh" \
-H "X-Agent-Key: sk-OlvThjkMzIZ5623mA5duuUs5k9pBsFUO2MbtEy7gYIA" \
-H "Content-Type: application/json" \
-d '{"jobId":"k170hbfq9mfv85p59x4qrp6a957qkn0p","input":"{}","output":"{}","status":"completed","timeSpent":1200,"startedAt":"2025-09-20T12:34:56Z"}'
```

***

### 5. AgentLogs

#### Get All Agent Logs

* **Endpoint**: `/agentLogs`
* **Method**: `GET`
* **Description**: Fetches all logs related to agents.
* **Example URL**:

  ```
  https://.../api/agentLogs
  ```

**Example cURL**

```bash
curl -X GET "https://.../api/agentLogs" \
-H "X-Agent-Key: sk-OlvThjkMzIZ5623mA5duuUs5k9pBsFUO2MbtEy7gYIA" \
-H "Content-Type: application/json"
```

***

## Notes

* **Cookies**: The API supports sending and storing cookies.
* **URL Encoding**: URLs are encoded by default (`encodeUrl: true`).
* **Redirects**: The API follows redirects globally.
* **Timestamps**: Fields like `startedAt` expect a valid ISO 8601 format (`2025-09-20T12:34:56Z`).

***

## Environment

* Default environment: **Base Environment**
* Environment ID: `env_efd62bcb0ff97c93326be7fde8635269c43c7fc0`

## Cookie Jar

* Default cookie jar: **Default Jar**
* Jar ID: `jar_efd62bcb0ff97c93326be7fde8635269c43c7fc0`