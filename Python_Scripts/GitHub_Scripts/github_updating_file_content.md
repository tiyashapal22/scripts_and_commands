# Updating File Content In GitHub

## Code

```Python

import requests
import base64

def getting_sha(url,token):
    response = requests.get(url,
                         headers={'Authorization': 'Bearer '+token, 'Content-type': 'application/json'},
                         verify=True)
    data = response.json()
    return str(data['sha'])

def base64encoading(s):
    string_bytes = s.encode('UTF-8')
    base64_bytes = base64.b64encode(string_bytes)
    base64_string = base64_bytes.decode('UTF-8')
    return base64_string


## The File location
## Example : "https://api.github.com/repos/tiyashapal22/Python/contents/GitHub_Scripts/test.md"
url ="https://api.github.com/repos/{username}/{repo}/contents/{path}"

## GitHub API Token
token = "<token>"

## Data to be written
content = """# Heading 1

## Heading 2

### Heading 3

- Data 1
- Data 2
- Data 3
- Data 4
"""

## Creating JSON Payload
payload = '{"message": "Automated Update","content": "'+base64encoading(content)+'","sha": "'+getting_sha(url,token)+'"}'

## GET Request
response = requests.put(url,
                         headers={'Authorization': 'Bearer '+token, 'Content-type': 'application/json'},
                         data = payload,
                         verify=True)

data = response.json()

## Response Status
print("\nResponse :",response)

## File Name
print("\nFile Name : "+str(data['content']['name']))

## File SHA
print("\nSHA : "+str(data['content']['sha']))

## File Size
print("\nFile Size : "+str(data['content']['size']))

## File URL
print("\nFile URL : "+str(data['content']['html_url']))

## File Download Link
print("\nFile Download Link : "+str(data['content']['download_url']))

## Committer Author
print("\nAuthor : "+str(data['commit']['author']['name']))

## Committer Mail
print("\nMail : "+str(data['commit']['author']['email']))

## Commit Time
print("\nTime : "+str(data['commit']['author']['date']))

```