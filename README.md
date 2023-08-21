# Writing Studio
A practice web app to improve writing skills in some language.

## Screenshots
<img width="1300" alt="ShowPage1" src="https://github.com/runpumeng/WritingStudio-Django/assets/112782995/851a619e-96f1-4659-9f0b-58786511c7f6">

<img width="1306" alt="ShowPage2" src="https://github.com/runpumeng/WritingStudio-Django/assets/112782995/7bb092b2-8512-4e2b-a753-e41731ea0d66">

## Pre-requisites
We would need following installed in our system before we start with setting up the project in local machine.
1. Git - This is needed as a version control system. If you don't have this preinstalled in local machine, visit https://git-scm.com/downloads and setup git on local.
2. Python 3 - We are using Python as a programming language in this project. Mac and Ubuntu have it pre-installed. NOTE: you might have Python 2 on your Mac or Ubuntu. If so, make sure to download Python 3.

## Local Setup
1. Clone this repository into local system and change the directory.
   
```sh
git clone https://github.com/runpumeng/WritingStudio-Django.git
cd WritingStudio-Django/
```
2. Install pip3 and pipenv.

```sh
pip3 install pipenv
```
3. Go into the virtual environment: 
   
```sh
pipenv install
pipenv shell
```
4. Apply migrations
   
```sh
python manage.py makemigrations
python manage.py migrate
python manage.py loaddata languages.yaml
# NOTE: you can produce the same data in languages.yaml with
# python manage.py dumpdata users.Language --format=yaml > languages.yaml
```

5. Set up Twitter

For this, first, set up your environment variables.

You can take a look at .bash_profile_sample on how to set them up.

Then, run:

```
python manage.py shell < setup_twitter.py
```

On Heroku:

```
heroku run manage.py shell

exec(open("./setup_twitter.py").read())
```

6. Run the server:

```sh
python manage.py runserver <PORT>
OR
python manage.py runserver
```

7. Start the application opening the link shown in your terminal on a browser.
