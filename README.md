# Laravel Class Standards

## Introduction

It is very common for developers to be confused when it comes to classes, namespaces, methods and even variables.

With that in mind, this package was built to share a line of thought and help better organize your _Laravel_ projects.

Initially only the written tips will be made and, later, the package will also validate your project.

## Models

By default, _Laravel_ creates the _Models_ directly in the `app` folder. Or in the `App` namespace, if you prefer.  
Example: `php artisan make:model Product`.

However, it is possible to create the files in a specific folder, such as _Models_, for example.  
Just use the command as follows: `php artisan make: model Models/Product`.  
In this case the namespace is `App\Models`.

There is no right or wrong in this case. It is up to the developer to organize as they prefer. It is only recommended to follow the same pattern for everyone.

To name the file, always use singular words. Ever!