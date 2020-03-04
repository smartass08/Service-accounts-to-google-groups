This method is for generating ServiceAccounts from cloud.google.com and adding them to personal google groups.





## First setup AutoRclone from given link and enable drive api to get your credential.conf from it. (Skip this if you have your Service Accounts json files or have another method)

https://github.com/xyou365/AutoRclone

install all the required files and dependencies by following its readme.md file and create N numbers of ServiceAccounts (here N refers to quantity like 100/ 200 /300 etc)

Copy the accounts folder found in root directory of AutoRclone folder to somewhere safe. (This is important)

```

## Now we will procure the - ["client email": "xxxx@yyy.iam.gserviceaccount.com",] line from all the .txt files we created

Open PowerShell and cd into the root of copied accounts folder

Type:-
```
(Select-String -Path *json -Pattern 'client_email').Line | Set-Content Output.txt
```
Open the Output.txt file which is generated in notepad or any text editor of your choice

Remove the the text ``"client_email": "`` using find and replace tool 

This will remove everything except ``xxxx@yyy.iam.gserviceaccount.com,``

The final result will be unique email addresses with a comma at the end in each Line



For linux users-

``grep -oPh '"client_email": "\K[^"]+' *.json > emails.txt``

SAVE IT

## Head over to Google groups and create new group

Under member section, Select ``Direct add members`` and copy paste 10 email accounts from our new email .txt into the checkbox and submit

Since google group can only add 10 members in one time and 100 in a day, plan it accordingly to your Service Accounts emails and submit them

THATS IT.
