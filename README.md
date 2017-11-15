# MessageTemplaterPackage
# How to Run the Program
1. Unzip the MessageTemplaterPackage to a folder on your computer
2. Open a terminal to the folder that contains the unzipped artifacts
3. Start the REST Service by typing “java -jar MessageTemplater-1.0.jar” in the terminal.  Spring Boot will start the REST Service using port 8080.
4. Start the front end by opening “index.html” located in the “public.html” folder.  Chrome would provide the best experience.

# Design Decisions
1. Model Objects.  I modeled the solution with 4 objects: Company, Guest, MessageTemplate and a Reservation.  A guest has a reservation as part of its definition.
2. Data Access Objects.  To get data from the JSON files I created 3 interfaces CompanyDao, GuestDao and MessageTemplateDao.  I then created 3 implementations against those interfaces that do the real work.  If the data layer were to change we could create new implementations for those changes.  Given the project requirements the only methods implemented are getAll and getById for each Dao.
3. Controllers.  There are three REST controllers (Guest, Company, and MessageTemplate) that serve the information requested by the browser.
4. Tests.  I created tests for each Dao implementation to ensure I was getting the right data from the files provided.
5. Front End. Decided on html, Bootstrap CSS, and Javascript for the user to craft messages.  

# Languages
1. I chose Java for the back end because I used it while at the Software Guild and with the help of Spring I knew I could produce a RESTful webservice with minimal effort.
2. I chose Javascript and jQuery for the front end because I needed the practice with those tools.
Validation Process
3. I used Junit tests for each Dao implementation to ensure I was getting the right information from the JSON data files.
4. I manually tested the front end to validate the behavior I desired.

# Future Enhancements
Given more time I would make the following changes
1. Implement dependency injection into the backend so that I could change Dao implementations by changing an XML file.
2. Ensure that the solution works with all browsers.  I only tested with Chrome.
3. When the user inserts a message variable (e.g. <Company>, etc) by clicking the hyperlink under the Message Customization textarea, I would like it to get inserted at the cursor location rather than the end of the message template text.
4. Form validation.  Warn the user that certain dropdowns have not been selected after they click the “Generate Message” button.
5. Allow the message to contain more than one of the same type of message variable. The function that converts from message template to actual message only replaces one instance of a message variable.
6. Implement Javascript promises rather than calling one ajax from another ajax.
