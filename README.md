# Heatmap
Analysis of wind data correlations using Python, Pandas, Seaborn, and Matplotlib.
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt

df = pd.read_excel('Data_Wind_Clean232.xlsx')

cols = [
    'AmbientTemperature_value',
    'NacelleAngle_value',
    'WindDirection_value',
    'WindSpeed_value'
]

corr = df[cols].corr()

plt.figure(figsize=(8, 6))

sns.heatmap(
    corr,
    annot=True,
    cmap='coolwarm',
    vmin=-1,
    vmax=1,
    fmt='.2f',
    linewidths=0.5
)

plt.show()
