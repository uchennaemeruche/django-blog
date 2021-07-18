# Sample Django Deployment to Heroku

Tutorial: Steps to deploy this sample django blog project to Heroku

For detailed information about this project see the associated [MDN tutorial home page](https://developer.mozilla.org/en-US/docs/Learn/Server-side/Django/Deployment).

## Overview

This is a sample web application for a blog. It allows users to create new blog posts, browse posts, edit/update post and manage their accounts.

Some of the features ares:

- Models for posts and users
- Guest users can view blog posts and their details
- Only logged in/authenticated users can create/edit a blog post

## Prerequisites

To get started, you'll need the following:

- Github account.
- Heroku account (The free tier will do just fine).
- A development environment with python3 and pip installed.
- Note: The use of Python virtual environment is recommended. Follow this article to setup your [Python development environment](https://developer.mozilla.org/en-US/docs/Learn/Server-side/Django/development_environment)

## Quick Start

1. Clone this repository into your local development environment:
   `git clone https://github.com/uchennaemeruche/django-blog.git `
2. Change directory to the cloned repo. ` cd django-blog`
3. Activate your virtual environment. see [Python development environment](https://developer.mozilla.org/en-US/docs/Learn/Server-side/Django/development_environment)
4. You can optionally install the packages(dependencies specified in the requirements.txt).
   `pip install -r requirements.txt`
5. Test your project to make sure everything is working:
   ` python manage.py runserver`
6. Create a .env file and add the following:

   ```
       DJANGO_SECRET_KEY=your_django_secret_key_here
       DJANGO_DEBUG=False
   ```

7. Commit and push your changes to your github repo.
   ```
       git add .
       git commit -m "Initial commit"
       git push origin master
   ```
8. Download and install the Heroku client by following the [instructions on heroku here](https://devcenter.heroku.com/articles/getting-started-with-python#set-up)

9. Check that the cli installed successfully:
   `heroku help`
10. create and upload the website to heroku
    `heroku create`
11. Push the app to heroku
    ` git push heroku master`
12. Start a one-off heroku dyno and run database migrations
    `heroku run python manage.py migrate`
13. Create an admin super user to manage the database, create/update/delete posts
    `heroku run python manage.py createsuperuser`
14. Finally, open up the website using:
    `heroku open`
