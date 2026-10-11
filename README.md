# Assignment: Adding Razor Components to a Blazor Application

## Introduction

In this assignment, we will practice modifying Razor components. Specifically, we will make necessary changes to one Razor component so it displays data according to the requirements. We will also make sure that the component we modified is visible in the UI.

## Requirements

The solution contains a Blazor project based on the stand-alone WebAssembly template. It has two Razor components representing pages:

* `Home.razor`, which represents the home page of the application.
* `Products.razor`, which displays a list of electronic products.

At the moment, the home page doesn't display anything meaningful and the products page doesn't display any products. Moreover, the products page isn't even visible in the UI. Therefore, we will need to fix these issues by implementing the requirements below.

### Making the products page visible

The first thing we will do is make sure the `Products` razor component is displayed on the home page. However, we won't just copy and paste the content from the `Products.razor` component to the `Home.razor` component. We will reference the product component on the home page.

We will need to remove all renderable content from the home page. However, we need to keep intact the Razor directive responsible for the navigation to the home page.

### Loading data on the products page

Once we can display the `Products` razor component, we will need to make sure the data is loaded. To load the data, we will need to add an appropriate lifecycle event override method and populate the `products` array inside this method.

The data can be loaded from the `products.json` file in the `sample-data` folder of the `wwwroot` folder. We can deserialize the content of this file into an array of `Product` instances by invoking the `GetFromJsonAsync<T>()` method on the `Http` service that is injected into the component. In this case, `T` is a type that represents an array of `Product` instances. The parameter of this method is the relative path to the `products.json` file, assuming that the `wwwroot` folder is the root of the application and we are at the root.

> **Note:** The starter project created from the Blazor WebAssembly stand-alone template uses the same technique for loading weather data in the `Weather` component. Also, we need to remember that this method is asynchronous, so we will need to use the `async` and `await` keywords as appropriate.

## Deliverables

The deliverable of this assignment is the Blazor application with changes applied as per the requirements.

## Conclusion

Understanding the fundamentals of how Razor components are structured is a crucial skill and acts as a foundation that more advanced Blazor knowledge can be built upon. This assignment provided an opportunity to practice these fundamentals.