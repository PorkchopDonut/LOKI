# LOKI (Logistical Organizer for Keeping Inventory)      
-------------------------------------------------------------
    Concepted and programmed by: Logan Willis          
-------------------------------------------------------------
                                                             
# Description:                                               
                                                             
LOKI is a piece of software that started out as a Microsoft Access macro, written in VBA.  Its goal was to alleviate the time-consuming and inefficient inventorying process that the Precision Measurement Equipment Laboratory at Eglin Air Force Base was utilizing at the time to take stock of the equipment that was tied to their account.  At that time, a card catalog system was being used to track each individual piece of equipment and it would take two inventory monitors three months to fully accomplish a complete inventory of the laboratory.

When LOKI was originally developed as an Access macro, it would store the inventory in an Access database and provide the user with the capability of querying results by Stock Number (NSN), PMEL ID Number (PID), or by Document Number (DOC).  A basic user interface presented the data in a much more visually pleasing manner and, when coupled with a barcode scanner, LOKI was capable of reducing the time it took to inventory the lab from three months to three days.        

At a later point, LOKI was then updated from an Access macro to a Windows Form Application.  All the code was ported over to C# and the UI was improved dramatically.  The functionality improved even more and the quality of life provided by the program increased exponentially.  LOKI in its current stage is a result of all the subsequent updates and additions.

_____________________________________________________________

# Requirements:                                               
                                                             
LOKI is currently in the form of a Windows Executable file and has been tested and proven operational on the following versions of Windows:                              

    - Windows XP
    - Windows 7
    - Windows 10

Additionally, LOKI requires two pieces of data at a minimum to operate at its full capacity.  This includes the most current master_id.xml file from PAMS and a copy of the most current ReportServlet.txt file from the Equipment Management system.  Dialog prompts are used to fetch these files, so nomenclature does not matter.

_____________________________________________________________
                                                             
# Instructions:

LOKI is a self-sufficient executable file that can be run from anywhere on the computer.  It is most effective if it is stored on a shared drive to be accessed from any computer connected to the network, but note that the inventory file does not update in realtime and must be saved for any changes to take effect.  If multiple people are using different instances of LOKI at the same time, one of the instances' work will be wiped as if it were never performed in the first place.  Accordingly, it is important to ensure that only one person is actively using it to take an inventory at a time.

Upon initially loading up LOKI, if no inventory file is detected, it will initiate a new inventory and prompt the user for the most current versions of the two files noted in the "Requirements" section above.  After receiving both of those pieces of data, it will merge them into an inventory file saved in a "Current" folder created in the same directory as the executable.  The user will then be brought to the main landing page of the LOKI interface.  At this point, no actual inventory has been taken and, therefore, no PIDs will be tied to any NSNs or DOC numbers.  Queries can still be run for base NSN and DOC number information, but PIDs can only be reviewed after they have been tied to an NSN.  This is done by querying an NSN and clicking on the "Add New ID" button.  After a PID is tied to an NSN, that PID can be queried as well.

The "Auto-Scan" function in LOKI provides the user with a loop of prompts, one for an NSN query and one for a PID entry.  Provided the user is utilizing a USB barcode scanner for their inventorying process, this function enables the user to scan the alternating barcodes on all tracked items in an automated fashion to eliminate the need for a partner to click on buttons and answer prompts for each new PID entry.

When it is appropriate to initiate a new inventory, the "New Inventory" button can be located in the Administrator menu (accessed via the "Administrator" button on the main screen).  This will save the current inventory file in the "Archive" folder (created in the same directory as the executable) and create a fresh inventory file, prompting the user once more for current data files.  Additionally, if at any point the user desires to save a copy of the data files being used by the current inventory, these can be exported from the Administrator menu as well.

As R14 entries are completed, it could be desirable to print off R14 cards for later viewing.  This can be done in one of two ways.  The first is by the "Print Card" button on the main panel, which will print the currently displayed R14 entry.  The second is with the "Batch Print" function found in the Administrator panel, which will automatically cycle through all of the R14 entries in the current inventory and print off a card for each one.  Both of these functions will set up default page settings to comply with the appropriate stationary and print settings required for R14 cards and send these print jobs directly to the printer set as default for the workstation that LOKI is running on, so it is very important that the user ensures their default printer is set to an appropriate device.

Throughout an inventorying process, it might be beneficial to the user to have a print-off containing their progress to hunt down elusive items.  Should this be the case, LOKI is also equipped with an Excel Export function, with which the user can generate an Excel workbook that contains three worksheets, each respectively displaying all R14 entries that have either been under-scanned, over-scanned, or completed.  This Excel sheet can then be further modified or printed off as a physical tracker of progress.  This function can be accessed from the Administrator panel by clicking the "Export Excel" button.

Upon completion of or in the midst of an inventory, it is also possible to import and query from previous inventories.  This helps the user to analyze their results from the past to help them determine where underscanned entries may be located.  This is done by clicking on the "Query Previous" button.  The user will be prompted to save their progress on the current inventory and will then be prompted to locate a previous inventory to import.  Once the previous inventory has been imported, the user can query the data that the inventory contains but can not edit it in any way.  The "Query Previous" button will change to a "Back to Current" button and clicking on it again will return the user to the current inventory and all editing functionality will be restored once more.

-------------------------------------------------------------
LOKI is not an officially licensed or registered product, nor are its contents or the views of its creator representative of the Air Force or any members of the PMEL at Eglin AFB, FL.
-------------------------------------------------------------
