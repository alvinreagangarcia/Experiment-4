# Experiment-4

Part A
```python
df = pd.read_excel("board2.xlsx")
```
Load the exam dataset from Excel.
```python
instru_df = df.loc[(df["Track"] == "Instrumentation") & (df["Hometown"] == "Luzon"), :].copy()
```
From the dataset, I selected only the students whose track is instrumentation and hometown is Luzon.
```python
instru_df.loc[:, "Electronics >70"] = instru_df["Electronics"]
```
I created a column called “Electronics >70”, which shows their Electronics score.
```python
Instru = instru_df.loc[:, ["Name", "GEAS", "Electronics >70"]]
```
I kept only the needed columns "Name, GEAS, Electronics grade"

```python
print("Instru DataFrame:")
print(Instru)
```
I displayed the Instru DataFrame.

Part B 
```python
bd = pd.read_excel("board2.xlsx")
```
Reload the dataset (fresh copy).
```python
bd["Average"] = bd[["Math","Electronics","GEAS","Communication"]].mean(axis=1)
```
Calculate each student’s average score across Math, Electronics, GEAS, and Communication.
```python
mindy = bd.loc[(bd.Hometown=="Mindanao") & (bd.Gender=="Female") & (bd.Average>=55),
               ["Name","Track","Electronics","Average"]]
```
Pick only female students from Mindanao whose average score is 55 or above, then keep Name, Track, Electronics, and Average.
```python
print(mindy)
```
Display the Mindy DataFrame.
