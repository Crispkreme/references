## Reinforcement by AppExchange

**Purpose of learning**
Once you have completed this unit, you will be able to:

- Devise your own AppExchange strategy.
- Install the application from AppExchange.

**What is AppExchange?**
-  Salesforce has a community of partners that leverage the flexibility of the Salesforce Platform to build great applications and other solutions for everyone.
- Applications and solutions for these partners can be obtained from AppExchange and have (free and paid ), which can be installed.

![App Exchange](../images/basics-saleforce-platforms/app-exchange-1 "App Exchange")

**Strategy for success**
Develop an appropriate AppExchange strategy with the following steps:

- Identify the department that will use Salesforce or the department that will be used. People in these departments will be the main actors.
- Investigate which of the products available on AppExchange will meet the needs of stakeholders to the fullest extent. Discuss business cases with department heads and identify your needs. Below are some good questions.
    - What business problem are you trying to solve?
    - What are your most struggling points now?
    - How many users need this application?
    - How much is your budget?
    - What's going on with the timeline?
    **Note:** Asking these questions will help you find the best application for each department or business case.

- If you find an application that suits your needs, download it to the test environment (Free Developer Edition or Sandbox ). By installing this application, make sure it does not interfere with other installed applications or executed customizations. Sandbox is a copy of your organization in another environment. Used for development and testing."Sandbox Species and Templates"See documentation.
- If you choose from multiple applications, carefully consider what you have tested. Determine if there are no functions that cannot be used or unnecessary functions. If necessary, ask the stakeholders to demonstrate or provide feedback on the application.
- Now you're ready. Install and release the application in production. Communicate your changes to the user without delay and provide training and documentation as needed.

**First application installation**
- AppExchange is very similar to traditional application stores on mobile phones and tablets, but it's important to remember that the Salesforce organization has a complex environment.

![App Exchange](../images/basics-saleforce-platforms/app-exchange-2 "App Exchange")

- Whether to install the application in production or Sandbox? It is usually best practice to first install the application in a non-production environment. Try to install it on your production Sandbox or Developer Edition organization. If you first test the application, you can avoid conflicts such as object names in production environments.
- Which of the system administrators only, all users, and specific profiles do you want to grant application permission? It depends on who the application is for. If you want to limit access to some specific users, plan to change the target user's profile before installing the application.

**Row of installed applications**
The application is installed using a package. Here are the steps to find the package:

- From [Settings ] [ Quick Search ] Type "Installed Package" in the box to select.
- Click the name of the installed package. This name is the same as on the AppExchange download page.
- **[View component ]** Click to see more information about the package. The package details page shows all components of the package, including custom items, custom objects, and Apex classes. Based on this information, you can determine if each customization has no conflict.