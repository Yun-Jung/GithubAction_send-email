
Github Action for sending email
===

## Secrets required for Github Action
* Set GMAIL_USERNAME variable
> This variable is Sender's email account
* Set GMAIL_PASSWORD variable
> This variable is Sender's email password
* Set DOCKERHUB_USERNAME variable
> This variable is Dockerhub username
* Set DOCKERHUB_TOKEN variable
> This variable is Dockerhub password



Edit yaml file
---
#### The yaml file is used to include files attached in the email
##### *Take config-fcre.yml as example*

```yaml=2
gmail:
  username:
  password:
  from: SCC
```
> "username" and "password" variables will be added by secrets when executing Github action. "From" variable is used as sender's name.


```yaml=6
email:
  sender: SCC
  subject: Daily FCR Forecast and Graphs
  body: "Hello from Jetstream 2!\n\nHere are today's forecast and graphs. Have a wonderful day!\n\nBests,\nSCC and CIBR Team"
```

> "Subject" variable is used to be email subject.
> "Body" variable will be shown as the content inside email.


```yaml=10
attachments_web:
    - prefix: https://github.com/FLARE-forecast/flare-dashboard/raw/main/docs/fcre_files/figure-html/bvre-ice-1.png
      infix:
      suffix:
```
> "attachments_web" variable is used to attach files from web.
> 'Prefix', 'infix', and 'suffix' can be blank.

```yaml=56
attachments_local:
    - prefix:
      infix:
      suffix:
```
> "attachments_local" variable is used to attach file from local inside container.
> 'Prefix', 'infix', and 'suffix' can be blank.

```yaml=57
recipients:
    - 
```
> "recipients" variable is used to fill with receivers' email address.
