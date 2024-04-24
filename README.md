# MIST 4610 Group Project 2
### Group Name:

Sp24_47114_Group 1

### Group Members:

Isabelle Kiser 
[@isabellekiser](https://github.com/isabellekiser)

Will Cobb 
[@wjc56122](https://github.com/wjc56122)

Bhavik Maniklal 
[@BhavikManiklal](https://github.com/BhavikManiklal ) 

Ty Marcinczyk 
[@TylerMar1](https://github.com/TylerMar1)

Ryan Schoessling 
[@rschoess3](https://github.com/rschoess3)

Jaiden Timmons 
[@jaidentimmons](https://github.com/jaidentimmons)


### Dataset Description:

The dataset, sourced from https://catalog.data.gov/dataset/crash-reporting-drivers-data, offers insights into crashes within Montgomery County, Maryland. The Dimensions of the dataset include 43 columns and 170,218 rows,  and it encompasses various facets of crash data. These include:

- Report information: comprising report number, local case number, ACRS report type, and agency name.

- Crash details: covering elements such as crash date/time, municipality, latitude, longitude, location, route type, road name, cross-street type, cross-street name, and off-road description.

- Involved parties: related non-motorist, person ID, driver at fault, driver substance abuse, non-motorist substance abuse, injury severity, driver's license state, and driver distraction status.

- Collision specifics: collision type, vehicle damage extent, vehicle first impact locations, vehicle second impact location, vehicle body type, vehicle movement, vehicle continuing direction, and vehicle going direction.

- Vehicle information: encompassing vehicle ID, vehicle year, vehicle make, vehicle model, and equipment problems.
Environmental conditions: covering weather, surface condition, light, traffic control, and speed limit.

- Special circumstances: comprising circumstance, involvement of driverless vehicles, and incidents involving parked vehicles.
While most columns consist of string data types, exceptions include local case number (integer), crash date/time (Date/Time), speed limit (integer), vehicle year (integer), and longitude & latitude (decimal number).

Using this dataset has allowed us to construct comprehensive visualizations, enabling in-depth analysis of crash-related trends and patterns that helped us answer some important questions.


### Question 1:
How does the hour of the day influence the prevalence of sobriety and substance abuse in reported crashes in Maryland, and are there specific locations in Maryland where sobriety and substance abuse incidents are markedly more frequent?

The question regarding how the hour of the day influences the prevalence of sobriety and substance abuse in reported crashes in Maryland, and the identification of specific locations where these incidents are markedly more frequent, holds significant importance in many dimensions. Socially, pinpointing temporal and geographical patterns can facilitate targeted public awareness campaigns, fostering a cultural shift towards more responsible behavior and enhancing community safety. Economically, understanding these patterns helps mitigate the substantial costs associated with crashes, such as medical expenses and productivity losses, by enabling more effective preventive measures. From a public safety perspective, this data allows for strategic planning and resource allocation, such as increasing law enforcement presence during high-risk periods and improving road safety in prone areas, thus preventing accidents and saving lives. This multifaceted importance underscores the value of the data in driving informed decisions and interventions.

### Data Set Manipulation:
Our first question involves analyzing drivers who were sober vs under the influence so we needed to use the "Driver Substance Abuse" data column in our dataset. This column originally had 12 different variables including:
1. ALCOHOL CONTRIBUTED
2. ALCOHOL PRESENT
3. COMBINATION CONTRIBUTED
4. COMBINED SUBSTANCE PRESENT
5. ILLEGAL DRUG CONTRIBUTED
6. ILLEGAL DRUG PRESENT
7. MEDICATION CONTRIBUTED
8. MEDICATION PRESENT
9. N/A
10. NONE DETECTED
11. OTHER
12. UNKNOWN

Our group needed to isolate all variables that included being impaired into one group that contrasted with the crashes where nothing was present. To do this we created this calculated field:

IF [Driver Substance Abuse] = 'UNKNOWN' OR [Driver Substance Abuse] = 'N/A' THEN NULL ELSEIF[Driver Substance Abuse] = 'NONE DETECTED' THEN 'Sober' ELSE 'Under the Influence' END

We named this field "Sober vs Under the Influence" and while using it we filtered out "OTHER", "UNKNOWN", "N/A", and "NULL" in order to purely compare sober vs under the influence crashes. Creating this calculated field was critical in enabling us to visualize exactly what we wanted to through our graphs.

### Graphs:
<img width="628" alt="Screenshot 2024-04-24 at 3 28 57 PM" src="https://github.com/isabellekiser/Group1Project2/assets/150088753/ef0fa98e-b59f-4af5-8017-c7c89c66e584">

<img width="624" alt="Screenshot 2024-04-24 at 3 30 06 PM" src="https://github.com/isabellekiser/Group1Project2/assets/150088753/39cd0b3f-1add-4806-bef7-8849cca40cff">


### Question 2:
How does the extent of vehicle damage correlate with the severity of injuries sustained by occupants in Maryland, and how might the inclusion of vehicle movement at the time of the crash affect these outcomes?


![image](https://github.com/isabellekiser/Group1Project2/assets/150094078/0a963636-9334-4e95-8b1b-412b7a8ff1f7)

![image](https://github.com/isabellekiser/Group1Project2/assets/150094078/c05d4179-9dec-4be3-b569-8a21dbc1ccfe)

![image](https://github.com/isabellekiser/Group1Project2/assets/150094078/26000876-d2b6-4d2e-97d6-4d1f8d11a6f5)

If the extent of vehicle damage correlates with the severity of injuries sustained by occupants, these visualizations could potentially be used to evaluate the effectiveness of vehicle safety features.

### Manipulations applied to the data set for analysis:
if any
