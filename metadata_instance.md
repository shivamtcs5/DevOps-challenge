# To query metadata of an Azure instance and retrieve the information in JSON format, you can use the Azure Instance Metadata Service (IMDS) endpoint. Here's an example Python code snippet to achieve this:

```python
import requests
import json

metadata_url = "http://169.254.169.254/metadata/instance?api-version=2021-04-01"
metadata_headers = {"Metadata": "true"}

response = requests.get(metadata_url, headers=metadata_headers)

if response.status_code == 200:
    metadata_json = response.json()
    print(json.dumps(metadata_json, indent=4))
else:
    print("Error retrieving metadata. HTTP status code: ", response.status_code)
```

The code sends an HTTP GET request to the IMDS endpoint at `http://169.254.169.254/metadata/instance` with the specified API version. It includes a metadata header in the request to indicate that we want to retrieve instance metadata. 

If the response status code is 200, indicating a successful response, the code converts the JSON response to a string and prints it out in a nicely formatted way using the `json.dumps()` function with the `indent` parameter set to 4.

Note that this code assumes that it is running on an Azure instance that has access to the IMDS endpoint. If you are running the code elsewhere, you may need to modify the URL or headers to access the endpoint.
