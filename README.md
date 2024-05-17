# Python API Request to GitLab

This project focuses on making API requests to GitLab using Python. It demonstrates how to fetch data from GitLab's API and process the response.

## Installation:

To run this project, you'll need to install the `requests` module from PyPI.

```bash
pip install requests
```

## Fetching the Application API

**1. Obtain the GitLab API Endpoint:**

- The API documentation can be found at: GitLab API v4 Documentation.
- Append the GitLab user ID to the endpoint to fetch user-specific data. For example:

```ruby
  https://gitlab.com/api/v4/users/aminaahmed-cloud/projects
```

## Implementation

# Using 'requests.get()'

```python
import requests

response = requests.get("https://gitlab.com/api/v4/users/aminaahmed-cloud/projects")
print(response.text)
print(type(response.text))
```

<img src="https://i.imgur.com/1xk64ei.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>



# Using 'response.json()' for JSON Data

```python
import requests

response = requests.get("https://gitlab.com/api/v4/users/aminaahmed-cloud/projects")
print(response.json())
print(type(response.json()))
print(response.json()[0])
```

<img src="https://i.imgur.com/UjizHPj.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>



# Final Code

```python
import requests

response = requests.get("https://gitlab.com/api/v4/users/aminaahmed-cloud/projects")
my_projects = response.json()

for project in my_projects:
    print(f"Project Name: {project['name']}\nProject Url: {project['web_url']}\n")
```

<img src="https://i.imgur.com/oOOL1rN.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>


This code snippet fetches the projects associated with the specified GitLab user (aminaahmed-cloud) and prints the project names and URLs.
