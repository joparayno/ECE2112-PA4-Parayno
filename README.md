# ECE2112-PA4-Parayno

This experiment seeks to identify the essential codes and functions required for data cleaning and visualization. Subsequently, these skills will be applied to develop a Python program for data wrangling and visualization.

## Table of Contents
* [Prerequisites](#Prerequisites)
* [Getting Started](#Getting-Started)
* [Experiment 4](#Experiment-4)
* [ECE BOARD EXAM PROBLEM](#ECE-BOARD-EXAM-PROBLEM)
* [Conclusion](#Conclusion)
* [Authors](#Authors)
* [Version History](#Version-History)

## Prerequisites 
* Physical server or virtual machine.
* CPU: 2 x 64-bit, 2.8 GHz, 8.00 GT/s CPUs or better.
* Memory: minimum RAM size of 32 GB, or 16 GB RAM with 1600 MHz DDR3 installed, for a typical installation with 50 regular users.
* Client environment may be Windows, macOS or Linux.
  
## Getting Started

You must first install Anaconda Navigator from https://www.anaconda.com/download to install Jupyter Notebook. 

### Mac
1. Visit the site for Anaconda Navigator.
2. Press Download and select your Mac Architecture.
   * Intel Processor (This is for devices that have an Intel Processor).
   * Apple ARM M1 or M2 (This is for devices that have Apple Silicon specifically for M1 or later).
3. Execute the file and it will ask for you if you trust it and press 'Allow'.
4. Agree to the Terms and Conditions and press Install.
5. Click continue and you can now delete the installer.
6. Open Anaconda Navigator and Launch the Jupyter Notebook.

### Windows
1. Visit the site for Anaconda Navigator.
2. Press Download and select Windows.
3. Save the exe file and run the installer.
4. Press the next button until you see the Install button and press Install.
5. Once you’ve installed Anaconda Navigator, open it and launch the Jupyter Notebook.

### Linux
1. Visit the site for Anaconda Navigator.
2. Select Linux
3. Copy the bash (.sh file) installer link.
4. Use wget to download the bash installer.
5. Run the bash script to install Anaconda3.
6. source the .bash-rc file to add Anaconda to your PATH.
7. Start the Python REPL.

## Experiment 4

### Instructions:

Download the ECE Board Exam 2 dataset found on this link: bit.ly/ECEBoardExamDataset and write a
Python script/code in the Jupyter Notebook to do the given problems. You may submit your Jupyter
notebook in the dedicated submission bin.

## ECE BOARD EXAM PROBLEM
To successfully complete this problem, I used the data wrangling and data visualization techniques along with storytelling in order for me to analyze the data  and present different (i) data frames; and (ii) visuals using the dataset given.

### To Start

```
import pandas as pd

df = pd.read_excel("board2.xlsx")
df['Average'] = df.mean(numeric_only=True, axis=1)
df
```

I first imported pandas as pd and added a DataFrame containing the data from the Excel file "board2.xlsx", I then added a new code that adds column 'Average', and stores the mean of numerical values for each row, resulting in the following data.

![Screenshot 2024-09-17 at 4 58 44 PM](https://github.com/user-attachments/assets/60674ced-9ebf-43d2-bd9b-8339d042c6cf)

### 1. Create the following data frames based on the format provided:
Example: Vis = [“Name”, “Gender”, “Track”, “Math<70”]; hometown is constant as Visayas
```
Vis = df[(df['Hometown'] == 'Visayas') & (df['Math']<70)][['Name', 'Gender', 'Track', 'Math']]
Vis
```
The code provided above should be the format for the subsequent codes. This should result in an output similar to the one shown below.

![Screenshot 2024-09-17 at 5 00 05 PM](https://github.com/user-attachments/assets/43ed622a-6775-45b4-8db2-a4d11fc6f5f9)

#### a. Filename: Instru = [“Name”, “GEAS”, “Electronics >70”]; where track is constant as Instrumentation and hometown Luzon

```
Instru = df.loc[(df.Track=="Instrumentation") & (df.Hometown=="Luzon") & (df.Electronics>70), ['Name', 'GEAS', 'Electronics']]
Instru
```



![Screenshot 2024-09-17 at 5 05 55 PM](https://github.com/user-attachments/assets/14801282-e9ae-4b83-a201-a133a82ee26d)

#### b. Filename: Mindy = [ “Name”, “Track”, “Electronics”, “Average >=55”]; where hometown is constant as Mindanao and gender Female

```
Mindy = df.loc[(df.Hometown == "Mindanao") & (df.Gender=="Female") & (df.Average>=55), ['Name', 'Track', 'Electronics']]
Mindy
```



![Screenshot 2024-09-17 at 5 06 22 PM](https://github.com/user-attachments/assets/5711565d-e6b2-4494-9d43-9859e8d36bfa)

### 2. Create a visualization that shows how the different features contributes to average grade. Does chosen track in college, gender, or hometown contributes to a higher average score?

To create a visualization, it’s crucial to use the code provided below. As it enables the student to generate and visualize graphs for data representation.

```
import matplotlib.pyplot as plt
```

```
plt.figure(figsize=(5,5))
plt.bar(df['Track'], df['Average'])
plt.xlabel("Chosen Track in College")
plt.ylabel("Average")
plt.title("A bar graph illustrating the correlation between the Chosen Track in College and its impact on the average grade.")
```

The code above generates a graph that visually represents the correlation between the Chosen Track in College and its impact on the average grade. The resulting graph resembles this:

![Screenshot 2024-09-17 at 5 09 13 PM](https://github.com/user-attachments/assets/983787ac-8b5e-4e28-b2c9-0b329407d5d8)

```
plt.figure(figsize=(5,5))
plt.bar(df['Gender'], df['Average'])
plt.xlabel("Gender")
plt.ylabel("Average")
plt.title("A bar graph illustrating the correlation between gender and average grade.")
```

The code above generates a graph that visually represents the correlation between gender and average grade. The resulting graph resembles this:

![Screenshot 2024-09-17 at 5 10 24 PM](https://github.com/user-attachments/assets/db78207e-2fd6-43b4-ab07-770fe3285dd0)

```
plt.figure(figsize=(5,5))
plt.bar(df['Hometown'], df['Average'])
plt.xlabel("Hometown")
plt.ylabel("Average")
plt.title("A bar graph illustrating the correlation between hometown and average grade.")
```

The code above generates a graph that visually represents the correlation between hometown and average grade. The resulting graph resembles this:

![Screenshot 2024-09-17 at 5 11 13 PM](https://github.com/user-attachments/assets/d9bd9f26-2401-4b1d-ad2a-385bab24e43c)

## Conclusion

Based on the illustrations from the three graphs above, we can observe that the chosen track in college, gender, or hometown can indeed influence the average grade:
- From the first graph, the track Microelectronics shows better in the average grade.
- From the second graph, it becomes evident that females have higher grades than males.
- From the third graph, it’s evident that individuals residing in Luzon have higher average grades.

## Authors
Jarrel Parayno (jarrel.parayno.eng@ust.edu.ph)

## Version History
* 0.2
  * Updated the README.md file
* 0.1
  * Updated the README.md file
  * Created a README.md file
  * Initial Release 
