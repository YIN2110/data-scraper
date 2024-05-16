# udemy-data-scraper
Project for retrieving course information from Udemy using their Affiliate API
# Udemy Data Scraper

This project aims to retrieve course information from Udemy using their Affiliate API. The collected data will include course titles, descriptions, instructors, and ratings, which will be used to create a comprehensive educational resource database. This will help users find and compare online courses effectively.

## Project Objectives

- Retrieve course information from Udemy.
- Parse and store the data in a structured format.
- Provide a user-friendly interface to search and compare courses.

## How to Use the Udemy API

To use the Udemy Affiliate API, follow these steps:

1. **Register for API Access**:
   - Visit the [Udemy Developer Portal](https://www.udemy.com/developers/affiliate).
   - Register for an API client and provide the necessary information.
   - Once approved, you will receive your `client_id` and `client_secret`.

2. **Authenticate and Fetch Data**:
   - Use the provided credentials to authenticate and fetch course data.
   - Below is an example code snippet to get you started.

### Example Code

```python
import requests
import base64

# Replace with your actual client_id and client_secret
client_id = 'your_client_id'
client_secret = 'your_client_secret'

# Generate the basic authentication header
auth = base64.b64encode(f'{client_id}:{client_secret}'.encode()).decode()

headers = {
    'Authorization': f'Basic {auth}',
    'Content-Type': 'application/json'
}

# Send request to Udemy API to fetch courses
response = requests.get('https://www.udemy.com/api-2.0/courses/', headers=headers)

if response.status_code == 200:
    data = response.json()
    # Print the retrieved data
    print(data)
else:
    print(f"Failed to retrieve data, status code: {response.status_code}")

    data = response.json()
    print(data)
else:
    print(f"Failed to retrieve data, status code: {response.status_code}")
