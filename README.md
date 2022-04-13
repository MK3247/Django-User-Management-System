# Django User Authentication/Registration System

This project focuses on user management using Django Authentication Framework. It is a simple management application that allows users to:
* Register accounts,
* Log in,
* Change their passwords, and
* Reset their Password 

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
