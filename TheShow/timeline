import matplotlib.pyplot as plt
import numpy as np
from datetime import date, timedelta

# Data
dates = [
    date(2020, 1, 20), 
    date(2020, 2, 6), 
    date(2020, 3, 13), 
    date(2020, 3, 17), 
    date(2020, 4, 3), 
    date(2020, 4, 28),
    date(2020, 9, 23),
    date(2020, 12, 11),
    date(2020, 12, 21),
    date(2021, 1, 8),
    date(2021, 3, 6),
    date(2021, 8, 3)
]

# Extend min_date and max_date by some days for better visualization
min_date = min(dates) - timedelta(days=20)
max_date = max(dates) + timedelta(days=20)

# Labels
labels = [
    'First recorded \ncase in the US', 
    'First recorded Covid-19\n death in the US', 
    'Covid-19 outbreak\n is declared \n a national emergency', 
    'All 50 states have \nconfirmed Covid-19 cases', 
    'CDC recommends wearing \n face masks in public', 
    'US reports more \nthan 1 million cases',
    'More contagious \nstrain is discovered',
    'FDA begins issuing \nemergency use \nauthorization \nfor vaccines',
    'Vaccine distributions \nbegins',
    'US surpasses \n300,000 \ndaily cases',
    '3 million Americans receive \na vaccine in one day',
    '70% of Americans have \nreceived at least one shot'
]

# Labels with associated dates
labels = ['{0:%d %b %Y}:\n{1}'.format(d, l) for l, d in zip(labels, dates)]

# Plot
fig, ax = plt.subplots(figsize=(20, 6), constrained_layout=True)
ax.set_ylim(-2, 1.75)
ax.set_xlim(min_date, max_date)
ax.axhline(0, xmin=0.05, xmax=0.95, c='deeppink', zorder=1)

ax.scatter(dates, np.zeros(len(dates)), s=120, c='palevioletred', zorder=2)
ax.scatter(dates, np.zeros(len(dates)), s=30, c='darkmagenta', zorder=3)

# Custom offsets for labels
label_offsets = [0.6, -0.7, 0.4, -1.8, 1.1, -0.8, 0.5, -2, 0.7, -0.8, 0.5, -0.7]

# Add annotations
for i, (l, d) in enumerate(zip(labels, dates)):
    offset = label_offsets[i] * 100  # Adjust multiplier as needed
    ax.annotate(l, (d, 0), xytext=(0, offset), textcoords='offset points',
                ha='center', fontfamily='serif', fontweight='bold', color='royalblue',
                fontsize=12, arrowprops=dict(arrowstyle="->", color='royalblue'))

# Stems
stems = np.zeros(len(dates))
stems[::2] = 0.3
stems[1::2] = -0.3   
markerline, stemline, baseline = ax.stem(dates, stems, use_line_collection=True)
plt.setp(markerline, marker=',', color='darkmagenta')
plt.setp(stemline, color='darkmagenta')

# Hide lines around chart
for spine in ["left", "top", "right", "bottom"]:
    ax.spines[spine].set_visible(False)

# Hide tick labels
ax.set_xticks([])
ax.set_yticks([])

# Title
ax.set_title('Important Milestones in the Covid-19 Pandemic', fontweight="bold", fontfamily='serif', fontsize=16, color='royalblue')

# Show the plot
plt.show()
