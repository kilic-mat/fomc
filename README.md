# fomc

# We examine the short-term impact of Federal Open Market Committee (FOMC) announcements on technology stocks behavior. Using a modified continuous-time simulation model, we analyze high-frequency data for nine representative stocks from July # 2019 to January 2021, covering ten FOMC announcement dates and the outbreak of COVID-19. High-frequency data provides more insight than lower frequent data. 


import matplotlib.pyplot as plt
import seaborn as sns

# Jumpt sensitivity of Stocks acc. to FOMC annoucements

heatmap_data = {
    'Date': [
        '2019-07-31', '2019-09-19', '2019-10-31', '2020-04-29',
        '2020-06-10', '2020-07-29', '2020-09-16', '2020-11-05',
        '2020-12-16', '2021-01-27'
    ],
    'AAPL': [3.3504, 2.1773, 3.2206, 3.6643, 3.7094, 3.5048, 0, 3.2103, 2.89, 1.7553],
    'MSFT': [2.7244, 3.1539, 3.7408, 2.5929, 3.5806, 2.9858, 3.5118, 3.2924, 3.1076, 2.4575],
    'AMZN': [2.1044, 2.0733, 2.2042, 1.04031, 1.479, 1.5252, 2.1632, 1.7852, 2.1961, 1.9139],
    'CSCO': [2.7592, 3.2434, 1.2241, 3.9282, 2.9327, 3.1781, 2.9998, 0.0723, 0, 2.3796],
    'PEP':  [2.5274, 2.1309, 2.3032, 2.0828, 2.2815, 2.2464, 0, 3.2629, 0.1093, 1.6348],
    'QCOM': [1.319, 1.6775, 2.4113, 1.1168, 1.5164, 1.4767, 0.7241, 1.4505, 1.7814, 1.4643],
    'CHKP': [0.1174, 0.063, 0.0965, 0.0786, 0.0922, 0.1949, 2.9998, 1.361, 1.6258, 1.2948],
    'INCY': [0.8819, 0.6948, 1.91, 0.4342, 0.8138, 0.7525, 1.3897, 0.761, 1.7188, 0.7065],
    'FOX':  [0, 0, 0.104, 0.0368, 0.0467, 1.5031, 0.0838, 0.0723, 0.1056, 0.0472]
}

df_heat = pd.DataFrame(heatmap_data)
df_heat.set_index('Date', inplace=True)

plt.figure(figsize=(12, 8))
sns.heatmap(df_heat, annot=True, cmap='YlGnBu', cbar=True)
plt.title('Heatmap of Stock Jump Activity Across FOMC Announcements')
plt.xlabel('Stocks')
plt.ylabel('FOMC Announcement Dates')
plt.show()
