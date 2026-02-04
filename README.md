# World-Population
import pandas as pd
import seaborn as sns # Statistical data visualization library for Python
import matplotlib.pyplot as plt

df = pd.read_csv(r"C:\Users\sriha\Downloads\world_population (2).csv")
df

pd.set_option('display.float_format', lambda x: '%.2f' %x)

df.info()

df.describe()

df.isnull().sum()

df.sort_values(by = "2022 Population", ascending = False).head()

df.corr(numeric_only=True)

sns.heatmap(df.corr(numeric_only = True), annot = True)
plt.rcParams['figure.figsize'] = (20,7)
plt.show()

df.groupby('Continent').mean(numeric_only = True)

df[df['Continent'].str.contains('Oceania')]

df2 = df.groupby('Continent').mean(numeric_only = True).sort_values(by= "2022 Population", ascending = False)
df2

df.columns

df2 = df.groupby('Continent')[['1970 Population',
       '1980 Population', '1990 Population', '2000 Population',
       '2010 Population', '2015 Population', '2020 Population',
       '2022 Population']].mean(numeric_only = True).sort_values(by= "2022 Population", ascending = False)
df2

df3 = df2.transpose()
df3

df3.plot()

df.boxplot(figsize=(20,10))

df.select_dtypes(include='number')

df.select_dtypes(include='object')




