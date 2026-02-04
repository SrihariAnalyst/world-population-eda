# World-Population
import pandas as pd
import seaborn as sns # Statistical data visualization library for Python
import matplotlib.pyplot as plt

df = pd.read_csv(r"C:\Users\sriha\Downloads\world_population (2).csv")
df

pd.set_option('display.float_format', lambda x: '%.2f' %x)

df.info()

