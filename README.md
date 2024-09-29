# Helpdesk Ticket Generation

This project is a UIPath automation that 
allows us to automatically generate a 
ticket in the Zoho helpdesk software from an
Excel file.

The implementation mostly follows the book
**'Robotic Process Automation Projects'**
by _Nandan Mullakara_, with some improvements
added based on personal experience. Besides,
this automation is built with the modern UI
automation selectors as opposed to the book,
which uses the classic selectors. Furthermore,
this implementation of the automation is an unattended
automation and not an attended one, meaning it is built
to run without direct supervision on a virtual Windows
machine.

Zoho is a web application which follows
the SaaS model and provides a 
time-limited trial, available after
sign-up at <https://desk.zoho.com>.

## Input

The input looks as follows:

![input xlsx](https://github.com/anmv921/uipath-zoho/blob/main/Data/ZohoProcessScreenshots/05.PNG)

This table is called Request.xlsx and
it contains a single entry for ticket
creation. The fields are then:

- Contact name
- Contact email
- Ticket subject

The file location can be set in
Config.xlsx, located in the Data
folder.

## Zoho automation

The Zoho automation is composed of a few
steps.

First, the Zoho homepage must be open, and
then the RPA program needs to open the
ticket creation page by clicking on the
'+' button. The following screenshot shows
this page.

![tickets page](https://github.com/anmv921/uipath-zoho/blob/main/Data/ZohoProcessScreenshots/01.PNG)

Clicking on the button highlighted in green
opens the ticket creation form.

First we need to type in the name and the email
and scroll down to type the subject, as 
shown in the screenshots.

<img alt="ticket form 1" src="https://github.com/anmv921/uipath-zoho/blob/main/Data/ZohoProcessScreenshots/02.PNG" width="200" /> 

We need to select the status of the newly 
created ticket - 'Open'.

Other fields are optional and outside of
scope of this project.

After we have inserted the data obtained from
the input into the form we can click 
the submit button, highlighted in green.

<img alt="ticket form 2" src="https://github.com/anmv921/uipath-zoho/blob/main/Data/ZohoProcessScreenshots/03.PNG" width="200" />

If the ticket is created successfully then the
following page is shown:

![tickets page](https://github.com/anmv921/uipath-zoho/blob/main/Data/ZohoProcessScreenshots/04.PNG)

To return to the homepage, we click the '<'
button, highlighted in green.

## UIPath process

The process described above is implemented 
with the UIPath program.

The program consists of the following
components:

> ### ReadConfig.xaml
>
> - Reads the Config.xlsx 
> - Saves the data into the 
> dictionary of type <String, Object>

> ### ReadRequestExcel.xaml
>
> - Reads the request and saves the
> ticket info into string variables.
> 
> - If the request is not available,
> an exception is launched and the 
> workflow is terminated.

> ### ZohoAutomation.xaml
>
> - Opens the Zoho ticket creation form
>
> - Inputs the ticket data into the fields
>
> - Checks if the data was inserted
> correctly
>
> - Submits the form
> - Returns to the frontpage
> - Exits the ticket creation form
> in case of failure, returning to
> the homepage as well.

> ### ZohoClean.xaml
> - Clears the Zoho page and returns
> to the homepage in order to
> avoid errors with the creation of 
> any further tickets.

> ### Main.xaml
> - Combines all these workflows,
> - Checks if the ticket was created
> successfully.
> - In case of success, the Request.xlsx
> file is moved to 'Processed' folder,
> whose location can be defined in
> the Config.xlsx. 
> - The archived file is 
> renamed to the current date and time
> with the format
> "Request_yyyy-MMM-dd-HH-mm-ss.xlsx"

## Demo

The results of the RPA program can
be seen in the following video:

![demo gif](https://github.com/anmv921/uipath-zoho/blob/main/Data/Demo/demo2.gif)

***

***That's it!***

***Happy automation!***

***

<details>

<summary>TODO</summary>

- Add other fields to Zoho form
- Add a loop for multiple ticket creation
- Convert the project to REFramework
- Add annotations and logs
- Change the relevant variables to assets as opposed
to config values.
- Add a login workflow
- Draw.io diagram

</details>
