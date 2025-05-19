# Getting File Content From GitHub

## Code

```Python

import requests
import base64

def download_file(url,token):
    response = requests.get(url,
                         headers={'Authorization': 'Bearer '+token, 'Content-type': 'application/json'},
                         verify=True)
    return response.content.decode()


## The File location
## Example : "https://api.github.com/repos/tiyashapal22/Python/contents/GitHub_Scripts/test.md"
url ="https://api.github.com/repos/{username}/{repo}/contents/{path}" 


## GitHub API Token
token = "<token>"

## GET Request
response = requests.get(url,
                         headers={'Authorization': 'Bearer '+token, 'Content-type': 'application/json'},
                         verify=True)

data = response.json()

## Response Status
print("\nResponse :",response)

## File Name
print("\nFile Name : "+str(data['name']))

## File SHA
print("\nSHA : "+str(data['sha']))

## File Size
print("\nFile Size : "+str(data['size']))

## File URL
print("\nFile URL : "+str(data['html_url']))

## File Download Link
print("\nFile Download Link : "+str(data['download_url']))

## File Content
print("\nFile Content : \n"+download_file(str(data['download_url']),token))

```