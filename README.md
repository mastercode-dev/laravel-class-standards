# Laravel Class Standards

## Summary

 - [Introduction](#Introduction)
 - [Models](#Models)
 - [Controllers](#Controllers)
 - [Form Requests](#Form Requests)

## Introduction

It is very common for developers to be confused when it comes to classes, namespaces, methods and even variables.

With that in mind, this package was built to share a line of thought and help better organize your _Laravel_ projects.

Initially only the written tips will be made and, later, the package will also validate your project.

## Models

By default, _Laravel_ creates the _Models_ directly in the `app` folder. Or in the `App` namespace, if you prefer.  
Example: `php artisan make:model Product`.

However, it is possible to create the files in a specific folder, such as _Models_, for example.  
Just use the command as follows: `php artisan make:model Models/Product`.  
In this case the namespace is `App\Models`.

There is no right or wrong in this case. It is up to the developer to organize as they prefer. It is only recommended to follow the same pattern for everyone.

To name the file, always use singular words. Ever! Examples: `Product`, `Category`, `CategoryProduct` and so on.

## Controllers

**Namespace**

It is important to specify the _namespace_, when the system has different interfaces, with different functions, mainly.

Let's use the example of an e-commerce:
1. In the manager, it is possible to create, edit and remove products;
2. On the website, the customer can only list the products and view them;

In this case, the ideal is to create two _controllers_ with the same name, but in different _namespaces_: `.../Controllers/Manager/ProductsController` and `.../Controllers/Client/ProductsController`.

To add the _namespace_ to the _controller_ creation command: `php artisan make:controller Namespace/NameController`.

**Class**

In the _Laravel_ documentation, the examples of _controllers_ are always in the singular.

Our recommendation is that they be created in the plural, just to follow the pattern of the _routes_.
Anyway this will depend on the preference of the developer or the team.

The biggest issue here is that a _controller_ (almost) always references a _model_, whether singular or plural. So, if you have a `Product` _model_ create a `ProductController` or `ProductsController` to manipulate that _model_.

Of course there are exceptions, like `DashboadController` or `HomeController`, for example.

## Form Requests

As the application code grows, one of the important precautions is to keep the _form request_ classes well organized.

To do this the suggestion is quite simple, just follow the path of the _controllers_.

As well?

Let's suppose that we need to validate the `store` method located in `App\Http\Controllers\Admin\ProductsController`;

For this, we will create an `App\Http\Requests\Admin\Products\StoreRequest`;

The command to create this Request is: `php artisan make: request Admin/Products/StoreRequest`.