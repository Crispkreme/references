## Hands on Challenge
it can be used if you have a sales in different countries

## Youtube
- How to activate multiple currencies in Salesforce [YouTube](https://www.youtube.com/watch?v=6m9YhQEHhC8).
- Set Up the Exchange Rate In Prepare Your Salesforce Org for Users [YouTube](https://www.youtube.com/watch?v=hX3hqIdpnN4).
- Customize the Home Page [YouTube](https://www.youtube.com/watch?v=TCOY5YhNnHA).

## Validation of multi-currency
- go to the testing account
- https://wise-panda-9f3jl5-dev-ed.trailblaze.lightning.force.com/lightning/page/home

![Salesforce Organization](../images/salesforce-organization-preparation-for-users/saleforce-1.png "Salesforce Organization")

- open your account
- Gear icon Settings icon Click,[Setup (Settings )] Select.

[Salesforce Organization](../images/salesforce-organization-preparation-for-users/saleforce-2.png "Salesforce Organization")

- [Quick Find (Quick Search )] In Box Company Information Enter (organization information )
- [Company Information (Organization Information )] Select.

[Salesforce Organization](../images/salesforce-organization-preparation-for-users/saleforce-3.png "Salesforce Organization")

- click the **view this page in Salesforce Classic.**
- click the **Edit** button

[Salesforce Organization](../images/salesforce-organization-preparation-for-users/saleforce-4.png "Salesforce Organization")

- go down and find the **Currency Settings**
- then if you want to activate the currency just click the **Activate Multiple Currencies** checkbox.

[Salesforce Organization](../images/salesforce-organization-preparation-for-users/saleforce-5.png "Salesforce Organization")

- then click **Save button**
- then go back to the **Company Information**
- then click the **Currency Setup (Currency Settings )** button

[Salesforce Organization](../images/salesforce-organization-preparation-for-users/saleforce-6.png "Salesforce Organization")

- then click **New button**
- Set the euro using the following information:

| **Field (Item)**                         | **Value (value)**      |
| ---------------------------------------- | ---------------------- |
| Currency Type (By currency species)      | **EUR – Euro (Euro)**  |
| Conversion Rate (Conversion rate)        | 1.5                    |
| Decimal Places (Decimal point position)  | 2                      |

- then click **Save button**

## Test the exchange rate in a new business talk.
- go to the main home page
- then find the app launcher
- then look for the sales
- then click the sales

[Salesforce Organization](../images/salesforce-organization-preparation-for-users/saleforce-7.png "Salesforce Organization")

- look for **Close Deal**
- then click the **View Opportunities**

[Salesforce Organization](../images/salesforce-organization-preparation-for-users/saleforce-8.png "Salesforce Organization")

- look for **New button**
- then click it
- then enter the following details

| **Field (Item)**                               | **Value (value)**                                            |
| ---------------------------------------------- | ------------------------------------------------------------ |
| Opportunity Name (Trade name)                  | Euro Currency Test **(Euro currency test)**                  |
| Account Name (Trading Partner Name)            | United Oil & Gas, UK **(United Oil & Gas (United Kingdom))** |
| Opportunity Currency (Business talk currency)  | Euro **(Euro)**                                              |
| Close Date (Scheduled completion date)         | End of this month **(End of this month)**                    |
| Stage (Phase)                                  | Closed Won **(Commercialization)**                           |
| Amount (Amount)                                | 10000 **(0 is 4 pieces)**                                    |

[Salesforce Organization](../images/salesforce-organization-preparation-for-users/saleforce-10.png "Salesforce Organization")

- then click **Save button**

## Exchange rate update
- open your account
- Gear icon Settings icon Click,[Setup (Settings )] Select.

[Salesforce Organization](../images/salesforce-organization-preparation-for-users/saleforce-2.png "Salesforce Organization")

- go and find the [Quick Find (Quick Search )]
- then put type **Manage Currencies** in the search box 
- then press enter (Currency Management )

**Note:** [Quick Find (Quick Search )] [Manage Currencies (If you don't see currency management )]Company Information
[Salesforce Organization](../images/salesforce-organization-preparation-for-users/saleforce-11.png "Salesforce Organization")

- click the **view this page in Salesforce Classic.**
- click the **Edit Rates** button

[Salesforce Organization](../images/salesforce-organization-preparation-for-users/saleforce-12.png "Salesforce Organization")

- change the currencies base in the country you added
- then click **Save button**

## Test the exchange rate in a business talk.
- go to the main home page
- then find the app launcher
- then look for the sales
- then click the sales

[Salesforce Organization](../images/salesforce-organization-preparation-for-users/saleforce-7.png "Salesforce Organization")

- look for **Close Deal**
- then click the **View Opportunities**

[Salesforce Organization](../images/salesforce-organization-preparation-for-users/saleforce-14.png "Salesforce Organization")

- then just compare it to the previous
- then if its ok
- you completed the task

## Exchange rate update based on the conversion rate according to the calendar date
- open your account
- Gear icon Settings icon Click,[Setup (Settings )] Select.

[Salesforce Organization](../images/salesforce-organization-preparation-for-users/saleforce-2.png "Salesforce Organization")

- go and find the [Quick Find (Quick Search )]
- then put type **Manage Currencies** in the search box 
- then press enter (Currency Management )

**Note:** [Quick Find (Quick Search )] [Manage Currencies (If you don't see currency management )]Company Information
[Salesforce Organization](../images/salesforce-organization-preparation-for-users/saleforce-11.png "Salesforce Organization")

- click the **view this page in Salesforce Classic.**
- click the **Enable** button of the **Advanced Currency Management is not enabled**

[Salesforce Organization](../images/salesforce-organization-preparation-for-users/saleforce-15.png "Salesforce Organization")

- click the **Yes, i want to enable advance currency management** checkbox
- click the **Enable** button

[Salesforce Organization](../images/salesforce-organization-preparation-for-users/saleforce-16.png "Salesforce Organization")

- then look for the **Manage Date Exchange Rates** button

[Salesforce Organization](../images/salesforce-organization-preparation-for-users/saleforce-17.png "Salesforce Organization")

- click the checkbox
- click the **Continue** button

[Salesforce Organization](../images/salesforce-organization-preparation-for-users/saleforce-18.png "Salesforce Organization")

## Update the Exchange Rate with ACM
- open your account
- Gear icon Settings icon Click,[Setup (Settings )] Select.

[Salesforce Organization](../images/salesforce-organization-preparation-for-users/saleforce-2.png "Salesforce Organization")

- go and find the [Quick Find (Quick Search )]
- then put type **Manage Currencies** in the search box 
- then press enter (Currency Management )

**Note:** [Quick Find (Quick Search )] [Manage Currencies (If you don't see currency management )]Company Information
[Salesforce Organization](../images/salesforce-organization-preparation-for-users/saleforce-11.png "Salesforce Organization")

- click the **view this page in Salesforce Classic.**
- click the **Enable** button of the **Advanced Currency Management is not enabled**

[Salesforce Organization](../images/salesforce-organization-preparation-for-users/saleforce-15.png "Salesforce Organization")

- click the **Yes, i want to enable advance currency management** checkbox
- click the **Enable** button
- then look for the **Manage Date Exchange Rates** button

[Salesforce Organization](../images/salesforce-organization-preparation-for-users/saleforce-17.png "Salesforce Organization")

- **[New Exchange Rates (New conversion rate )]** Click to enter the item.
    - Start Date (Start date ): (First day of the following month )
    - Euro (Euro ): 1.13
- then click **Save button**
- then go back to the **Test the exchange rate in a business talk** to test

## Create a new home page using Lightning Application Builder

- open your account
- Gear icon Settings icon Click,[Setup (Settings )] Select.

[Salesforce Organization](../images/salesforce-organization-preparation-for-users/saleforce-2.png "Salesforce Organization")

- the go the find **Quick Find (Quick Search)** 
- then search for **Lightning App**
- click the **view this page in Salesforce Classic.**

[Salesforce Organization](../images/salesforce-organization-preparation-for-users/saleforce-19.png "Salesforce Organization")

- click the **New Button**
- then **Create a new Lightning Page**
- select the **Homepage**
- click the **Next Button**

[Salesforce Organization](../images/salesforce-organization-preparation-for-users/saleforce-20.png "Salesforce Organization")

- then write the **Support Home Page** in the label input
- click the **Next Button**
- select the **Standard Home Page (Standard Home Page )**

[Salesforce Organization](../images/salesforce-organization-preparation-for-users/saleforce-21.png "Salesforce Organization")

- search **Recent Items (Recently used data )**
- drag the components into any part of the canvass

[Salesforce Organization](../images/salesforce-organization-preparation-for-users/saleforce-22.png "Salesforce Organization")

- go to the Label then select the **Custom**
- then add the **Recent Cases** inside the Custom Label
- then find the **API Anomaly Event Store**
- then click the **Select**

[Salesforce Organization](../images/salesforce-organization-preparation-for-users/saleforce-23.png "Salesforce Organization")

- Select the left arrow and go to the **[Available (Available )]** column.
- **[Available (Available )]** From **[Case (Case )]** 
- Select and click the right arrow to go to **[Selected (Selected )]** column.

[Salesforce Organization](../images/salesforce-organization-preparation-for-users/saleforce-24.png "Salesforce Organization")

- click the **OK Button**
- then add **5** in **Number of Records to Display** input
- search **[Chatter Feed (Chatter Feed )]**
- drag the components into any part of the canvass

[Salesforce Organization](../images/salesforce-organization-preparation-for-users/saleforce-25.png "Salesforce Organization")

- change the **Feed Type** into **[To Me (To yourself )]** then select it.

[Salesforce Organization](../images/salesforce-organization-preparation-for-users/saleforce-26.png "Salesforce Organization")

- [Today’s Tasks ( Today's ToDo )] Drag the component anywhere on the canvas.
- [Today's Events (Today's behavior )] Drag the component anywhere on the canvas.

[Salesforce Organization](../images/salesforce-organization-preparation-for-users/saleforce-27.png "Salesforce Organization")

- [Rich Text (Rich text )] Drag the component to the box [Today's Tasks (Today's ToDo )]. A text entry item appears under the box.

[Salesforce Organization](../images/salesforce-organization-preparation-for-users/saleforce-28.png "Salesforce Organization")

- In this text input item,Be sure to check the Salesforce Trust site. (Be sure to check the Salesforce Trust site. ) Enter
- Salesforce Trust Highlight the text in[Link (Link )] Select a button.
- [URL]https://trust.salesforce.com Enter

[Salesforce Organization](../images/salesforce-organization-preparation-for-users/saleforce-29.png "Salesforce Organization")

## Activate new homepage

- click the **Save** button.
- click the **Activation** button.

[Salesforce Organization](../images/salesforce-organization-preparation-for-users/saleforce-30.png "Salesforce Organization")

- then **Activation: Support Homepage** modal will display
- then select the **App and Profile**
- then click the **Assign to Apps and Profile**

[Salesforce Organization](../images/salesforce-organization-preparation-for-users/saleforce-31.png "Salesforce Organization")

- then **Select Apps** modal will display
- check the **Service console**
- then click the **Next Button**
- then **Select Profiles** modal will display
- look for the **Custom: Support Profile (Custom: Support Profile )** and **System Administrator (System Administrator )**

[Salesforce Organization](../images/salesforce-organization-preparation-for-users/saleforce-32.png "Salesforce Organization")

[Salesforce Organization](../images/salesforce-organization-preparation-for-users/saleforce-33.png "Salesforce Organization")

- click the **Next** button.

## Create a new list view

- go to the main home page
- then find the app launcher
- then look for the sales
- then click the sales

[Salesforce Organization](../images/salesforce-organization-preparation-for-users/saleforce-7.png "Salesforce Organization")

- look for **Plan My Accounts**
- then click the **View Accounts**

[Salesforce Organization](../images/salesforce-organization-preparation-for-users/saleforce-34.png "Salesforce Organization")

- then look for the **List View Controls**
- then click for the **New** button

[Salesforce Organization](../images/salesforce-organization-preparation-for-users/saleforce-35.png "Salesforce Organization")

- Enter the following information in the section.
    - List Name (List name ): Energy and Biotech Accounts
    - List API Name: Energy_and_Biotech_Accounts
    - Who sees this list view (Who displays this list view ): All users can view this list view

[Salesforce Organization](../images/salesforce-organization-preparation-for-users/saleforce-36.png "Salesforce Organization")

- then click for the **Save** button

## Edit the search criteria for the list

- go to the filters.
- Filter by Owner (Narrow by Owner ): All accounts (All trading partners )
- click **Done** button

[Salesforce Organization](../images/salesforce-organization-preparation-for-users/saleforce-37.png "Salesforce Organization")

- click the **[Add Filter (Add search criteria )]**.
    - Field (Item ) = **Industry** (Industry )
    - Operator (operator ) = **equals** (Matches the following string )
    - Value (value ) = **Energy, Biotechnology** (Energy, biotechnology )
- then click the **Done** button.
- then click the **Save** button.

[Salesforce Organization](../images/salesforce-organization-preparation-for-users/saleforce-38.png "Salesforce Organization")

## Select the item to display

- List view control at the top right Gear icon Gear icon with down arrow Click
- [Select Fields to Display (Select item to display )] 
- Select
- [Available Fields (Selectable items )] From list [Industry (Industry )] Select
- [Add (Add )] Arrow (>Click ).
- [Save (Save )] Click.
- [Hide Filters (Hide search criteria )] 
- (Click the funnel icon in the upper right ).

[Salesforce Organization](../images/salesforce-organization-preparation-for-users/saleforce-39.png "Salesforce Organization")