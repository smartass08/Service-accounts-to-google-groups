## How to create service accounts and add them to your respected google groups.
<br />

### Generating service accounts

Setup all the required dependencies from below repo and follow the steps accordingly.

  1) Visit [here](https://github.com/xyou365/AutoRclone) (All credits to its owner)

  2) Install all the required files and dependencies by following its readme.md file and create any number of service accounts.

  3) Copy the accounts folder found in root directory of repo to somewhere safe. (This is important, Yes please don't share them on internet)

<br />

### Getting all emails

#### Windows :-

  1) Open PowerShell and cd into the root of copied accounts folder

  2) Execute:- `$emails = Get-ChildItem .\**.json |Get-Content -Raw |ConvertFrom-Json |Select -ExpandProperty client_email >>emails.txt`

This will give you all of your emails into `emails.txt` file 


#### For linux / MacOs users :-

  1)`grep -oPh '"client_email": "\K[^"]+' *.json > emails.txt`

This will give you all of your emails into `emails.txt` file 

<br />


### Adding to google your group  

  1) Create a new google group [here](https://groups.google.com) or use your any existing one.
  
  2) Under `member section`, Select `Add members` button (Don't forget to check `Directly add members`) and copy-paste 10 email accounts into the checkbox and submit . We are only adding 10 at a time because google's public api restricts us to add only 10 members in one time and 100 in a day, So plan it accordingly to your count of service accounts and add them in batches.

Anunay Maheshwari, [01-Oct-2020 at 8:43:41 PM]:


### License

This work is dual-licensed under Apache 2.0 and GPL 2.0 (or any later version).
You can choose between one of them if you use this work.

`SPDX-License-Identifier: Apache-2.0 OR MIT`
