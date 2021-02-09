# SPS-8714-Web-Application-Automation-
Web Application Automation 
Video link

https://drive.google.com/file/d/1WSBBRyYuSoTE1c-F13YvqO-BJcUvId_Z/view?usp=sharing

Project Description

Project Title: Web Application Automation  

Project Description:

In this project , we will build an process to automate an currency converter web application using blue prism. The excepted outcomes of this project are
Should launch the web application
Should able to take the values automatically from the Excel Sheet
Should be able to store the values back to the excel in the result column
Tool to be used
Blue Prism
Work flow: 
Launch the Web application
Create the Business Model and Spying HTML Elements into Application modular. 
After launching the Blue Prism, Open Studio tab, right-click on Objects, and select Create Object named it as “Web automation with excel”
Click on Application Modular and add Application Modular name same as business object created in step 1.
Select Browser-Based application (Chrome Browser) and next select a Browser that is to be launched from a .exe file. 
Browse .exe file of chrome browser and enter URL Address of Application window (https://www.xe.com/currencyconverter) by keeping all the next settings as it is. 
Finally test the Model by Clicking Launch Button.

Spy the Elements.
After tuning Application Modeller identify the following four elements from application website.
Identify (Amount) as “InputValue”, (From Currency) as “Form Currency”, (To Currency) as “To Currency”, (Next Button ‘>’) as “GO Button”,(Currency Converter Text) as “Convert data”, by Ctrl + left click. 
In the attributes tab, deselect the checkbox whose Value is empty. Deselect the Parent URL Attribute checkbox(the Parent URL attribute ticked in Application Modeller then the element will only be found for this URL, and when the page is revisited and the URL changes. Hence the process may crash.)

Creating the Pages, Launch right-click and “Input Value”.
Add navigation as “launch”. Drag “Web Automation T2 from application Explorer” into the Actions Element column. Set Action as Launch.
Create a action page “Input Value” with following data members
Create 4 Data Items 

1) Name: Input value Type: Number Initial Value: 100
 2) Name: Form Currency Type: Text Initial Value: USD 
3) Name: ToCurrency Type: Text Initial Value: CAD
                 4) Name: Value from Conver data Type: Text
Add the Wait stage in the canvas by dragging, rename it as “Wait” then Create Writer as “Enter Input write” by Dragging “Input value” from Data Explorer into the Actions Value column and Drag “Input Value” from Application Explorer into the Actions Element column. 
Repeat the step 4 and create writer as “Enter Form Currency”.
Add the Navigation stage in the canvas by dragging it and rename it as “Click”. Drag “Go Button” from application Explorer into the Actions Element column. Set Action as Click Center
Add the Reader stage in canvas by dragging, rename it as “Read Convert data”.
Open the End-stage Properties in canvas, add Output Name as ”Convert Data” and Get value From in “Value from Convert data” Data Item with “Text” data type and do proper connections

Publish the object studio pages
Publish the object studio launch and Input Value action page for deployment so that we can run it in process studio 

MS Excel VBO (Import VBO file)
File -> Import -> Browse -> (C:\Program Files\Blue Prism Limited\Blue Prism Automate\VBO\BPA Object - MS Excel). Click Finish.

Create Process Object as”Web Automation T2 Process”.
Create 2 Data Items Name: handle Type: Number Name: Workbook Name Type: Text and Create 1 Collection Name: Data
Create Action Stage as “Create XL Instance” (Business Object = MS Excel VBO; Action = Create Instance). Click on the Outputs tab, Create Data Item, type = number, name =” handle”. Drag it into Store In column, click on ok.
Create Action stage as “Open Work Book” (Business Object = MS Excel VBO; Action = Open Workbook). Click on the Inputs tab Drag “handle” data item into handle Value In column. Set file path of excel file in File Name Value column and Click on the Outputs tab, Create Data Item, type = Text, name = “Workbook Name”. Drag it into Store In column. Click on OK.
Create Action Stage as “Read from Workbook” (Business Object = MS Excel VBO; Action = Get Workbook as Collection). Click on the Inputs tab, Drag “handle” data item into handle Value column. Drag “Workbook Name” data item into the Workbook Name Value column. Write Worksheet Name as “Sheet1” and Click on the Outputs tab to Create Collection as “Data”.
Create Action stage as “Launch” (Business Object = Web Automation T2; Action = Launch).
Drag Loop module. Create Action as “Enter Data” (Business Object = Web Automation T2; Action = Input value)
Create Action stage as “Update Xl” (Business Object = MS Excel VBO; Action = Write Collection). Write Cell Reference as “A3”. Set Include Column Names as False.
Create Action stage as “Save and close” (Business Object = MS Excel VBO; Action = Close Workbook). Set Save Data Flag as “True”. Do Proper connections



Testing the Process Object from Object Studio
Click on Main Page, click on the Green play button to run the ‘Web Automation T2 Process’ Process object. It shows COMPLETED when there is no error or no failure in the object.

Output
Process Flow execution






Output Excel File



Advantages of  RPA using Blue Prism
Increased efficiency, 
Improved accuracy
Lower operational cost and elevated CX
Richer data analytics 
Higher employee productivity and satisfaction
Easier and agile process design 
Faster time to market. 

Project Repository
Includes Process Object File (Web Automation T2 Process.bpprocess) and Business Object (Web Automation with Excel.bpobject)
Snapshot of Application- Currency Website.jpg, Process Flow.jpg
Input Excel File: Book1.xlsx
Output: Output.jpg
Readme.txt-Includes the video link
https://drive.google.com/file/d/1WSBBRyYuSoTE1c-F13YvqO-BJcUvId_Z/view?usp=sharing
