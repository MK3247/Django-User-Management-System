# Django User Authentication/Registration System

This project focuses on user management using Django Authentication Framework. It is a simple management application that allows users to:
* Register accounts,
* Log in,
* Change their passwords, and
* Reset their Password 

![image](https://github.com/Django-User-Management-System/blob/main/register.jpg)

# Built With

* [Python 3.9.11](https://www.python.org/) - Programming Language 
* [Django](https://www.djangoproject.com/) - Framework Used
* [Bootstrap](https://getbootstrap.com/) - Frontend 

## Code Example

```python
def login(request):

    if request.method == 'POST':
        form = LoginForm(request.POST)
        if form.is_valid():
            cd = form.cleaned_data
            user = authenticate(
                request,
                username = cd['username'],
                password = cd['password']
            )
            if user is not None:
                if user.is_active:
                    auth_login(request, user)
                    return HttpResponse('Authenticated successfully')
                else:
                    return HttpResponse('Disabled Account')
        else:
            return HttpResponse('Invalid Login !!')
    else:
        form = LoginForm()

    return render (request, 'account/login.html', {'form':form})
```

## Installation

Clone this repository

```
git clone https://github.com/MK3247/Django-User-Management-System.git
```

Open the folder

```
cd Django-User-Management-System
```

Install all the requirements

```
python -m pip install -r requirements.txt
```

## Running the demo

```
python manage.py runserver
```

## To Receive Password Reset Links During Development

Open yout terminal/command prompt and run the following command

```
(venv) $ python -m smtpd -n -c DebuggingServer localhost:1025
```

## Contributions

1. Fork this repository.
2. Create a branch: `git checkout -b <branch_name>`.
3. Make your changes and commit them: `git commit -m '<commit_message>'`
4. Push to the original branch: `git push origin <project_name>/<location>`
5. Create the pull request.

Alternatively see the GitHub documentation on [creating a pull request](https://help.github.com/en/github/collaborating-with-issues-and-pull-requests/creating-a-pull-request).

## Bug / Feature Request

In case you find a bug, kindly open an issue [here](https://https://github.com/MK3247/Django-News-Aggregator/issues/new). Include your query and your expected results.

## Author 

* **[Charles Wafula](https://https://github.com/MK3247)** 

[![github follow](https://img.shields.io/github/followers/MK3247?label=Follow_on_GitHub)](https://github.com/MK3247)
[![twitter follow](https://img.shields.io/twitter/follow/codeveterun?style=social)](https://twitter.com/codeveterun)

## References

- [Real Python](https://realpython.com/django-user-management/)
- Django 3 By Example
