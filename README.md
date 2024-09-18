Problem Statement ID	 SHI1676

Problem Statement Title
Web-scrapping tool to be developed to search and report Critical and High Severity Vulnerabilities of OEM equipment (IT and OT) published at respective OEM websites and other relevant web platforms

Discription
Critical Sector organisations uses a number of IT and OT equipment (e.g. Networking and hardware device, Operating Systems, Applications, Firmware etc.). These devices/application come with vulnerabilities from time to time. There should be timely information sharing mechanism by which the concerned equipment users at critical sector orgs should be altered regarding any critical / high severity vulnerabilities in their equipment within the shortest possible time. Detailed description: The ICT components (HW/SW) being used by Critical Sector Organisations become vulnerable from time to time. These vulnerabilities can be categorised as Critical, High, Medium and Low. Any exploitation of these vulnerabilities can cause havoc in multiple Critical Sector Organisations where such vulnerable equipment are being used. Keeping in view of the above, there is a need to monitor all such vulnerability information published at the equipment’s OEM websites and also other relevant websites. Once a critical or high severity vulnerability information is published at OEM website or any other relevant website, the ‘to be developed scrapper’ will immediately take that vulnerability input along with possible mitigating strategy published in the website and send the information to predefined email id(s). Note: The NVD website publishes such OEM vulnerable information. But the same comes with a time lag. It is therefore needed to get such information directly from OEM websites and /or from other relevant websites where such vulnerable information is published almost in real time. Expected Outcome: An automatic script using open source tools to be developed for the OEM vulnerability information scrapping and reporting. Tool should know various vulnerability information published data formats/syntax at OEM websites (both for IT and OT hardware and application) and come up with optimum solution for monitoring and reporting of such vulnerability information. The output of the tool that will be emailed to pre-designated email id(s) is as per following (shared with example; all fields may not be available at the time of reporting): * Product Name: Chrome * Product Version: - NA * OEM name: Google * Severity Level (Critical/High): High * Vulnerability: The N-able PassPortal extension before 3.29.2 for Chrome inserts sensitive information into a log file. * Mitigation Strategy: Install patch from https://me.n-able.com/s/security-advisory/aArHs000000M8CCKA0/cve202347131-passportal-browser-extension-logs-sensitive-data * Published Date: Jan 2024 * Unique ID: CVE-2023-47131


1. Define Requirements:
Target Data: Identify which OEM websites and platforms publish vulnerability information (e.g., OEM security advisory pages, National Vulnerability Database (NVD), security forums, CERT advisories).
Scope: Focus on vulnerabilities categorized as "Critical" or "High Severity." Use severity ratings from platforms like CVSS (Common Vulnerability Scoring System).
Frequency: Decide how often you want to scrape the websites (daily, weekly, etc.).
Reporting: Format the output (e.g., CSV, JSON, email reports, dashboard) and identify whether it should integrate with security tools (SIEM, vulnerability management systems).


2. Technology Stack:
Programming Language: Python is ideal for web scraping due to its vast ecosystem of libraries like BeautifulSoup, Scrapy, and Selenium.
Web Scraping Libraries:
BeautifulSoup: For parsing HTML and XML documents.
Scrapy: For handling complex scraping needs and managing multiple pages.
Selenium: For dynamic content that requires interaction (e.g., JavaScript-rendered pages).
Requests: To make HTTP requests.
Database: Store results in a database (e.g., PostgreSQL, MongoDB, or even a flat file like CSV).
Task Scheduler: Use cron jobs (Linux) or Windows Task Scheduler for periodic scrapin

3. Identify Vulnerability Sources:
List OEM websites that publish vulnerability updates and advisories.
Identify platforms like:
NVD (National Vulnerability Database)
CVE (Common Vulnerabilities and Exposures)
US-CERT, ICS-CERT (for OT vulnerabilities)
Vendor-specific security advisory sites (e.g., Cisco, Siemens, Schneider Electric, etc.).
Ensure that you comply with the terms of service of these websites before scraping.

4. Web Scraping and Data Extraction:
Write Python scripts using Requests and BeautifulSoup/Scrapy to scrape each website.
Target key elements like vulnerability titles, CVE IDs, severity, description, affected products, and patches.
Use the CVSS score to filter out only Critical (9.0-10.0) and High (7.0-8.9) severity vulnerabilities.

5. Handle Dynamic Content:
If the OEM websites use JavaScript to render vulnerability information, integrate Selenium to navigate and extract the content.
Automate form submissions if required (e.g., filtering vulnerabilities by date or severity on the website).
6. Data Storage and Reporting:
Store the scraped data in a structured format (e.g., database, CSV, JSON).
Generate regular reports that highlight the vulnerabilities with severity ratings.
If required, integrate this data with tools like SIEM or vulnerability management platforms.
7. Notifications and Alerts:
Set up an email or message notification system (using smtplib for email or webhooks for Slack/Teams) to send alerts when new high or critical vulnerabilities are found.
Consider adding a dashboard for visualization using frameworks like Flask, Django, or third-party tools like Grafana.
8. Automation and Maintenance:
Schedule the scraping tasks with a cron job or task scheduler.
Implement error handling and logging to monitor the tool's performance.
Regularly check for website structure changes and update your scrapers as needed.

Additional Considerations:
Legal Compliance: Ensure that scraping OEM websites is legal and complies with their terms of service.
Rate Limiting: Some websites impose rate limits. Respect these limits by introducing delays between requests.
Proxy Management: Use proxies if scraping multiple websites to avoid IP blocking.

paper back and reference 
Web scraping technologies in an API world 
Daniel Glez-Peña, Anália Lourenço, Hugo López-Fernández, Miguel Reboiro-Jato, Florentino Fdez-Riverola
https://academic.oup.com/bib/article-abstract/15/5/788/2422275

Analysis Of Different Web Data Extraction Techniques
Momin Saniya Parvez; Khan Shaista Agah Tasneem; Shivankar Sneha Rajendra; Kalpana R. Bodke
http://www.i-csrs.org/Volumes/ijasca/2021.3.11.pdf


BOOKS

"Web Scraping with Python: Collecting Data from the Modern Web" by Ryan Mitchel
Topics Covered:
Data parsing with BeautifulSoup
Scraping dynamic content with Selenium
Using APIs and dealing with JavaScript
Advanced techniques like handling CAPTCHAs and managing cookies

"Data Wrangling with Python: Tips and Tools to Make Your Life Easier" by Jacqueline Kazil and Katharine Jarmul
Topics Covered:
Web scraping with Python and Scrapy
Parsing HTML and XML data
Data cleaning and transformation
Working with APIs

 "Web Scraping with Python: A Step by Step Guide to Extracting Valuable Information from Websites" by Alex Giamas
 Topics Covered:
Scraping with BeautifulSoup and Selenium
Project-based approach
Automating web scraping tasks
Handling complex scraping challenges
