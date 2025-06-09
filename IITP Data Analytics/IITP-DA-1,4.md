
# Structured and Unstructured data:
Structured and unstructured data are two different types of data that are sourced, collected and scaled in different ways. 

Structured data is highly organized and easily decipherable by machine learning algorithms. It is typically categorized as quantitative data and is managed using structured query language (SQL). Examples of structured data include dates, names, addresses and credit card numbers. Structured data is easily used by machine learning algorithms and business users. It is accessible by more tools compared to unstructured data.

However, Structured data has limited usage and storage options. It is generally stored in data storage systems with rigid schemas. Change in data requirements necessitate an update of all structured data.

**Unstructured data:** It has no predefined format or organization. It is more difficult to collect, process and analyze compared to structured data. Eg: text documents, images, email messages, word-processing documents, and PDF files.

It can be collected from various sources such as open-ended survey results, social media comments, and email messages.

# Collection of Data through IOT
Data collection using Internet of Things(IoT) involves the use of interconnected devices, sensors, and systems to collect data from the physical world and transmit it over the internet or other networks for storage, analysis, and decision-making.

## Sensors:
**Sensor Deployment**: IoT applications typically start with the deployment of various sensors and devices in the physical environment. These sensors can include temperature sensors, humidity sensors, motion detectors, GPS modules, cameras and many others, depending on the specific use case.

## Data collection using Sensors:
**Data Acquisition**: Sensors continuously monitor and collect data from the environment they are placed in. This data can be in the form of temperature readings, motion events, location coordinates, video feeds, or any other measurable parameter. The data is often in analog form and may need to be converted into digital format using analog-to-digital converters.

## Data Processing at the Source
**Data Processing at the edge:** In some IoT systems, data processing may occur at the edge, i.e., on the devices themselves. This can involve basic data filtering, aggregation, or the application of simple algorithms to reduce the volume of data that needs to be transmitted. Edge processing helps in conserving bandwidth and reducing latency.

## Data Transmission:
Processed or raw sensor data is transmitted to a central location or the cloud using communication protocols such as Wi-Fi, Bluetooth, cellular networks(3G/4G/5G), depending on the IoT application and network availability. 
## Data Storage
Cloud storage and processing: once the data reaches the cloud, it is typically stored in databases or data likes. Cloud-based servers and services them process, analyze and stone the  data. This can involve real-time date streaming, bitch processing and data warehousing technologies.

## Data Analysis :
IOT data can be analyzed for various purposes such is monitoring, predictive maintenance, anomaly detection, and more. Advanced analytic techniques, including machine learning and artificial intelligence, may be applied to derive valuable insights and patterns from the data.
## Data visualization
IOT platforms often provide dashboards and visualization tools to present the data in a user-friendly way. Users can monitor the data, set up alerts for specific events, and generate reports for decision-making.

## Smart Equipment 
IoT Systems can also be designed to provide real-time feedback and control. For example, based on sensor data, an IoT system might adjust the temperature in a smart thermostat, control the lighting in a smart home, or optimize the operation of industrial equipment.

## Security and Privacy

Given the sensitive nature of IoT data, security measures like encryption, access controls and secure authentication are crucial to protect data integrity and user privacy.

## Applications:
Data collection using IoT has a wide range of applications, including smart cities, industrial automation, agriculture, healthcare, environmental monitoring and more. It enables organizations and individuals to make data-driven decisions, automate processes, and improve efficiency in various domains.

# Collection of Data from Web and Network

Collecting data from the web and social networks involves various techniques and tolls and it's essential to ensure that data collection is done ethically and within legal boundaries. 

## Web Crawlers
Web crawlers, also known as spiders or bot are automated programs that browse websites and collect information. They follow links on webpages and index content for search engines. While web crawlers collect publicly available data, some websites have measures in place to block or limit web crawling.

## HTML Parsing
Web scraping involves parsing the HTML(Hyper Text Markup Language) structure of webpages to extract specific data elements, such as text, images and links. Tools like BeautifulSoup(Python) and Cheerio(JavaScript) are commonly used for this purpose.

Parser: A computer program that breaks down text into recognized strings of characters for further analysis.

## DOM
The Document Object Model(DOM) is a programming API(Application Programming Interface) for HTML and XML(Extensible Markup Language) documents. It defines the logical structure of documents and the way a document is accessed and manipulated.

## Data Scraping

Web scraping techniques can be used to collect public data from social media profiles and posts. However, scraping social media data may violate platform terms of service, so its essential to review and the comply with their policy

## Ethical Considerations:
- **Privacy**: Respect User privacy and adhere to privacy laws and regulations. Avoid collecting personal information without consent.
- **Terms of Service**: Review and comply with the terms of service of websites and social media platforms. Some platforms explicitly prohibit data scraping.
- **Data Usage**: Be transparent about how you intend to use the data and ensure it's for lawful and ethical purposes.
- **Data Quality:** Ensure the data you collect is accurate and reliable. Scraper errors or API limitations can affect data quality. 
- **Data Storage**: Securely store the data you collect to prevent data breaches or unauthorized access.
- **Frequency:** Be mindful of the frequency of data collection to avoid overloading servers or violating platform rate limits.