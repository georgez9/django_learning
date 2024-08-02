# Django Model-View-Template (MVT) Pattern

Welcome to Django Model View Template (MVT) pattern, Django’s implementation of the standard Model-View-Controller (MVC) pattern.

After watching this video, you will be able to: 

- Describe the Model-View-Controller pattern, and
- Describe the Django Model View Template pattern. 

## Model-View-Controller (MVC)

The MVC design pattern divides application logic into three components. 

- *Model* **accesses** and **manipulates** data but does not present data. Model may have **database interfaces** such as *SQL* or *ORM*, or it may use **business logic** to process raw data. 
- *View* **presents** data in various forms, such as visual elements in a **webpage**, a mobile **app user interface**, or as *JSON/XML* format.
- *Controller* **coordinates** between *Model* and *View*. It **routes requests, processes input, requests data *CRUD* from Model, and updates View**. 

<img src="assets/image-20240802002750420.png" alt="image-20240802002750420" style="zoom: 33%;" />

When a client application sends a request with inputs to *Controller*, *Controller* **routes the request**, **validates** and **processes the input**, **sends CRUD requests to ** *Model*, and **forwards data** to *View* to be presented.

## Django Model-View-Template (MVT)

In the Django framework implementation, there is **no explicit Controller**. Instead, the Django server itself performs this function. 

Django Model manages data modelling and database mapping as well as business logic to process data. Django *View* describes **which data is presented**, but **not how it is presented**. Typically, view delegates(授权) to a *template*, which **describes how the data is presented**. When a client sends a request, the Django server routes the request to the appropriate view based on **the Django URL configuration**. Thus, Django follows a **Model-View-Template**, or MVT, design pattern.

<img src="assets/image-20240802004306764.png" alt="image-20240802004306764" style="zoom:33%;" />

## Model, View and Template

As we have learned, Django *models* are **classes mapped to database tables**. Django Model APIs allow developers to perform CRUD on objects and developers can also write business logic in Django model classes as functions. 

In Django, a *View* is essentially a **Python function**. This function **takes a Web request** and **applies the necessary logic to generate a Web response**, such as the HTML contents of a Web page, a redirect, a 404 error, an XML document, an image, or any other Web response. Often, View interacts with Django Model to get required data in the form of QuerySet or objects to generate a Web response. 

Django uses a *template* to generate **dynamic Web pages** which are sent back and rendered in a user’s browser. The Django template contains **static HTML elements**, as well as **special Python code** describing how the dynamic content of HTML pages will be generated. 

## Recap

In this video, you learned that:

- The Django model differs from the traditional MVC pattern.
- In the Django Model-View-Template MVT pattern: 
  - Django framework acts as Controller.
  - Django View describes which data to present, and 
  - Django Template describes exactly how data is presented.