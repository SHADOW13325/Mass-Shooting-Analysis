# Mass-Shooting-Analysis
It is a step-by-step approach of visualizing the dataset of mass shooting by cleaning the data ,data wrangling and plotting(visualizing) various entities to obtain useful results
Mass Shootings in the United States of America (1966-2017) The US has witnessed 398 mass shootings in last 50 years that resulted in 1,996 deaths and 2,488 injured. The latest and the worst mass shooting of October 2, 2017 killed 58 and injured 515 so far. The number of people injured in this attack is more than the number of people injured in all mass shootings of 2015 and 2016 combined. The average number of mass shootings per year is 7 for the last 50 years that would claim 39 lives and 48 injured per year.
# 1) Data-Preparation
Firstly we need to know about the dataset.So,

![GetImage](https://user-images.githubusercontent.com/36708227/55288228-f5494200-53d1-11e9-9f0d-62909ab0d4eb.png)
        
There are 323 shootings and 21 features in the dataset.

    S# - Shooting# - descending order
    Title - Description about the shooting
    Location - location of the mass shooting
    Date - date of shooting
    Incident Area - Area where shooting occurred
    Open/Close Location - Whether the location is closed or opened
    Target - Targeted shooting or random one? If Targeted, who was targeted
    Cause - cause for the shooting
    Summary - brief summary of the shooting. Who shot and the background etc.
    Fatalities - how many were dead during/after the shooting
    Injured - how many were injured during/after the shooting
    Total victims - Fatalities + Injured
    Policeman Killed - Number of policeman killed
    Age - Age of the gunman
    Employeed (Y/N) - Was the gunman employed
    Employed at - If employed, employment details of the gunman
    Mental Health Issues - Was the gunman mentally ill?
    Race - race of the gunman
    Gender - gender of the gunman
    Latitude - locations latitude
    Longitude - locations longitude
    
## 2) Data Processing
Let's see the missing values first

![GetImage](https://user-images.githubusercontent.com/36708227/55288278-da2b0200-53d2-11e9-8d0d-bbc9a7873e8b.png)
    
There are 45 missing locations, 62 missing incident areas and 5 missing Target.
  a) Let's try to derive the location from summary. My logic is based on the assumption that some titles have city and state separated by comma and some titles just have the state.

  ![GetImage (1)](https://user-images.githubusercontent.com/36708227/55288288-f9299400-53d2-11e9-8989-63e382b12e3b.png)
    
  b) Next we will make state names from updated locations we have now.We will extract the abbreviated state names and and name them in full form.
  
  ![GetImage (2)](https://user-images.githubusercontent.com/36708227/55288300-12cadb80-53d3-11e9-88ac-b3ca09846494.png)

  c) Now let's update the redundant values i.e. data cleaning
      i) Cleaning column gender
      
  ![GetImage (3)](https://user-images.githubusercontent.com/36708227/55288314-5cb3c180-53d3-11e9-9793-aeb2747c5ab4.png)
                                                ==>
  ![GetImage (4)](https://user-images.githubusercontent.com/36708227/55288315-5e7d8500-53d3-11e9-8fec-4b09a5250723.png)
   
  Likewise doing it for columns Race, Mental Health Issues, Cause, open/close Location
      ii) In case of less redundant values we will group them by our use. Cleaning column Incident area.
      
  ![GetImage (5)](https://user-images.githubusercontent.com/36708227/55288316-60dfdf00-53d3-11e9-8b29-1883fb1e1cc9.png)
                                                 ==>
  ![GetImage (6)](https://user-images.githubusercontent.com/36708227/55288317-63423900-53d3-11e9-93e9-0806260a07a2.png)
      
  Likewise doing it for columns Target.
## 3) Exploratory Data Analysis
  
Now it's the time to visualize our data for which we have done all of the above shit and derive results from it. So what are we waiting for. Let's Go.
  ### i) Mass Shootings Vs Year
  
  ![GetImage (8)](https://user-images.githubusercontent.com/36708227/55288319-69381a00-53d3-11e9-891c-794f0e7fab91.png)
  
 <b>We can see that there is a highly change in shootings from 2015 onwards as compared to all other previous years.</b>
  
  Let's categorise Mass shooting over the years based on Fatalities, Injured, Total Victims and No of shootings.
  
  ![GetImage (9)](https://user-images.githubusercontent.com/36708227/55288320-6b9a7400-53d3-11e9-83d6-67e3d5bc5149.png)
  
  <b>We can see that there is a massive change in all 4 categories in the after years.</b>
  
  
  Maybe there is a connection between shootings and cause. Let's see it.
  
  ### ii) Mass Shootings Vs Cause
  No of Shootings
  
  ![GetImage](https://user-images.githubusercontent.com/36708227/55289412-27fc3600-53e4-11e9-95d6-4f6161fab6b6.png)
  
  Total victims in the shootings
  
  ![GetImage (1)](https://user-images.githubusercontent.com/36708227/55289414-2c285380-53e4-11e9-81ba-421115d3b15d.png)
  
  Mass Shootings Vs cause
  
  ![GetImage (4)](https://user-images.githubusercontent.com/36708227/55289419-39ddd900-53e4-11e9-8bbb-22492bef97e0.png)
  
  <b>We can see that the No of shootings are more in case of cause of pyscho and terrorism and the total no of victims are more in case of terroism</b>
  
  ### iii) Mass Shootings Vs Race
  
  ![GetImage (5)](https://user-images.githubusercontent.com/36708227/55289421-3c403300-53e4-11e9-8b86-07e36fb7ab33.png)
  
  <b>We can see that in both the cases i.e. no of shootings and total victims, White Race and then Black Race is most affected. But there is majority of White people and then black people and then minorities in USA. So we cannot derive any inference.</b>
  
  Let's take this analysis further and let's compare the cause with the Mental Health Issues.
  
  ### iv) Mental Health Issues vs Cause
  Let's visualize it for No of Shootings
  
  ![GetImage (6)](https://user-images.githubusercontent.com/36708227/55289422-406c5080-53e4-11e9-8b0b-adbccdaa02b0.png)
  
  Let's visualize it for Total Victims
  
  ![GetImage (7)](https://user-images.githubusercontent.com/36708227/55289423-42ceaa80-53e4-11e9-969d-a03f8f1a9d66.png)
  
  <b>We can see that No of casualities are more in case of the person has Mental Health Issues than the person not having Mental Health Issues.</b>
  <b>Unknown mental health state is a scary issue. There are many people with mental health issues due to abusive childhood, bullies, poisonous environment, job opportunities etc.</b>  
  
  ### v) Mass Shootings va State
  
  ![GetImage (8)](https://user-images.githubusercontent.com/36708227/55289424-46fac800-53e4-11e9-97e9-6124e958cdf4.png)
  
  Above figure is not giving us the big picture in terms of comparison. So let's take it down to another comparable plot.
  
  ![GetImage (9)](https://user-images.githubusercontent.com/36708227/55289425-49f5b880-53e4-11e9-8a57-b1620a6c6d6c.png)
  
  ### vi) Mass Shootings in School Area
  
  ![GetImage (10)](https://user-images.githubusercontent.com/36708227/55289427-4cf0a900-53e4-11e9-8cc5-32bc29adfdc1.png)
  
  Let's break it down to Target audience by shooters in School Area.
  
  ![GetImage (11)](https://user-images.githubusercontent.com/36708227/55289428-4f530300-53e4-11e9-8cd1-7dcc6f9b409a.png)

  
  As expected the target audience is School people and the random people there.So no new inference can be drawn.
  
  # Inference
  1) We can see that there is an increase in no of mass shootings between 1984-2000.After that the sudden increase in the no of mass shooting was seen in the year 2007 of Virginia Tech shooting. 2012 recorded highest no of casualities as compared to all previous years. 2015 and 2016 got a severe high no of shootings resulting in many more casualities. Although 2017 got less no of shootings but the victims were highest in that year till date. Main shooting in 2007 was Las Vegas strip concert mass shooting. It is only possible when there is an easy access to the guns to commom peple and its purchase is not controlled by the government
  2) There seems to be a big gap between identifying a person to be having mental health issue and really helping with the issue. Due to this problem it is highly unpredictable of person that he will shoot.abusive childhood, bullies, poisonous environment, job opportunities etc results in unpredictable mental status
  
  # solutions
  1) Limit the availability of guns in the market.
  2) For Mental health the society must maintain the good decorum among themselves which is quite impossible.
  
