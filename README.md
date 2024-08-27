# Helpdesk Ticket Generation

This project is a UIPath automation that 
allows us to automatically generate a 
ticket in the Zoho helpesk software from an
Excel file.

## Input

The input looks as follows:

![input xlsx](https://github.com/anmv921/uipath-zoho/blob/main/Data/ZohoProcessScreenshots/05.PNG)

This table is called Request.xlsx and
it contains a single entry for ticket
creation. The fields are then:

- Contact name
- Contact email
- Ticket subject

The file location can be configured in
Config.xlsx, located in the Data
folder.

## Zoho automation

The zoho automation is composed of a few
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


