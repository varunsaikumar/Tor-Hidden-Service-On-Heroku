## Tor-Hidden-Service-On-Heroku
![image](https://img.shields.io/badge/Heroku-430098?style=for-the-badge&logo=heroku&logoColor=white) ![image](https://img.shields.io/badge/Tor-7D4698?style=for-the-badge&logo=Tor-Browser&logoColor=white)

_Note: Tor is ending its support for version 2 (v2) Onion Services, and v2 onion sites have since been deprecated. Please refer to_ `tor v3` [Tor-Onion-Service-On-Heroku](https://github.com/sumithemmadi/Tor-Onion-Service-On-Heroku).
### Prerequisites
- 1 . `nodejs`
- 2 . `tor`  _v2_
- 3 . `php`
- 4 . `git`
- 5 . `heroku CLI`


### Install Heroku
- 1 . Create an account on  **[https://heroku.com](https://heroku.com)**.
- 2 . Install the Heroku CLI on your computer: <br/>**[https://devcenter.heroku.com/articles/heroku-cli](https://devcenter.heroku.com/articles/heroku-cli)**. 
<br/>Check that you have the `heroku-cli` installed by checking the version number in your terminal:
```bash
heroku --version
```
- 3 . Connect the `Heroku CLI` to your account by writing the following command in your terminal and follow the instructions on the command line:
```bash
heroku login
```

### Quick Start

- 1 . After installing `Heroku CLI` clone this repository.

- 2 . Clone the repo with below command
```bash
git clone https://github.com/sumithemmadi/Tor-Hidden-Service-On-Heroku.git
cd Tor-Hidden-Service-On-Heroku
```
- 3 . Create a heroku application
```bash
heroku apps:create App-Name
```
-  `heroku apps:create App-Name` this command creates the application as well as a git remote, that you can use to push your code to Heroku:
 
-  _Note: replace `App-Name` with  any other name._
```bash
$ heroku apps:create tor-hidden-service-on-heroku
Creating ⬢ tor-hidden-service-on-heroku... done
https://tor-hidden-service-on-heroku.herokuapp.com/ | https://git.heroku.com/tor-hidden-service-on-heroku.git
```
- 4 . Now enter the below command

```bash
heroku buildpacks:set https://github.com/heroku/heroku-buildpack-multi.git
```
- Add this buildpack to heroku.
This buildpack is used for Running multiple language buildpacks in sequence.which are mentioned in  `Aptfile` file.

- 5 . Copy your website `index.html` file to the folder `views`</br>

- 6 . Copy SHA from private_key which is located at `/var/lib/tor/hidden_service/`

   - `hostname`
   - `private_key`
   If you don't know where these files stored refer to **[https://2019.www.torproject.org/docs/tor-onion-service](https://2019.www.torproject.org/docs/tor-onion-service)**
  

- 7 .  Tor hidden services require  a private_key and it's SHA to generate  .onion name. You'll need to provide this as env vars.You can also edit config vars from your app’s Settings tab in the [Heroku Dashboard](https://dashboard.heroku.com):
  [![image](https://raw.githubusercontent.com/sumithemmadi/Tor-Hidden-Service-On-Heroku/main/IMG_20210821_121319.jpg)](https://dashboard.heroku.com)
  - `HIDDEN_SERVICE_PRIVATE_KEY`: The contents of a private_key file


- 8 . Deploy your changes to heroku
```bash
git add .
git commit -am "Tor hidden service"
git push heroku
```

- _Now your app is accessible over Tor_
- To know your .onion address
- Run the below command on terminal
```
cat /var/lib/tor/hidden_service/hostname
```
### My app
![IMAGE](/IMG_20210822_193557.jpg)
-  **[https://tor-hidden-service-on-heroku.herokuapp.com/](https://tor-hidden-service-on-heroku.herokuapp.com/)**
    
- Tor is ending its support for version 2 (v2) Onion Services. Please refer to `tor v3` 
- GitHub Repo for `Tor onion service v3`:[https://github.com/sumithemmadi/Tor-Onion-Service-On-Heroku](https://github.com/sumithemmadi/Tor-Onion-Service-On-Heroku).


  
