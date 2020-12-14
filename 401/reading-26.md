# Getting Started with Django
https://www.djangoproject.com/start/

Object-relational mapper: rich, dynamic database-access API for free — but you can still write SQL if needed

URLs and views: a Python module called a URLconf which acts as a table of contents for your app, it contains a simple mapping between URL patterns and your views

Templates: a balance between power and ease, like working with HTML, but it is also flexible and highly extensible, allowing developers to augment the template

Forms: Django handles rendering forms as HTML, validating user-submitted data, and converting that data to native Python types

Authentication: handles user accounts, groups, permissions and cookie-based user sessions

Admin: reads metadata in your models to provide a powerful and production-ready interface that content producers can immediately use

Internationalization: full support for translating text into different languages, plus locale-specific formatting of dates, times, numbers, and time zones

Security: protections against:

- [x] Clickjacking

- [x] Cross-site scripting

- [x] Cross Site Request Forgery (CSRF)

- [x] SQL injection

- [x] Remote code execution


# How Django Works Behind the Scenes
https://wsvincent.com/how-django-works-behind-the-scenes/

Django is a Python-based web framework

originally developed at the Lawrence Journal-World newspaper by Adrian Holovaty, Simon Willison, and Jacob Kaplan-Moss

open source: open-sourced in 2005 and developers immediately started making contributions to the codebase

  two major issues that crop up are:
  
  - [x] funding
  
  - there are a host of decidedly less fun tasks needed to maintain and sustain an open source project: includes handling any legal/trademark issues, triaging tickets, guiding community discussions, organizing conferences, managing releases, and so on
  
  - Corporate Sponsor:a larger, for-profit company decide to open-source internal code
  
    - While this structure has the stability of a wealthy benefactor, there can be confusion around the licensing aspects at times
  
  - Solo: individual developer initially creates code, open sources it, and retains default control
  
    - the lead developer either raises contributions directly
    
    - offer add-on services
    
    - the founders provide highly-paid consulting services
  
  - Non-profit: formed to promote, support, and advance
  
  - [x] control

## Django Software Foundation
supports and maintains Django in a number of capacities

paid contractors who triage tickets, manage releases, and generally perform the unsexy but necessary work 

DSF also supports projects related to Django

The total budget for the DSF in 2019 is around $200,000

## Technical Organization
DSF handles legal, financial, and administrative matters for Django

Django has a small, core team of trusted volunteers who work alongside the Django Fellows to manage technical side of the Django Project
