# Mineralogical-Plots
Major oxide Plots 
#import pandas as pd
import matplotlib.pyplot as plt

# Manually input the data from the table again due to code environment reset
data = {
        "Oxides": [
        "SiO2", "CaO", "MgO", "SO3", "K2O", "Na2O", "TiO2",
        "MnO2", "P2O5", "Fe2O3", "Al2O3"
    ],
    "SiO2":     [43.5 ],
    "CaO":   [0.19],
    "MgO":     [0.089],
    "SO3":     [0.023],
    "K2O":     [0.122],
    "Na2O":     [0.001],
    "TiO2":    [0.30],
    "MnO2":    [0.044],
    "P2O5":    [0.18],
    "Fe2O3":    [52.32],
    "Al2O3":    [3.47],

}

# Convert to DataFrame
#df =pd.DataFrame(data)
df.set_index("Oxides", inplace=True)

# Transpose for plotting
df_t = df.transpose()

# Plot
ax = df_t.plot(kind="bar", figsize=(20, 10), width=0.85)
plt.title("MAJOR OXIDE DISTRIBUTION", fontsize=16)
plt.ylabel("Average (%)")
plt.xlabel("Locations (Lots)")
plt.xticks(rotation=45, ha="right")
plt.legend(title="Oxides", bbox_to_anchor=(1.05, 1), loc='upper left')
plt.tight_layout()
plt.grid(axis='y', linestyle='--', alpha=0.7)

plt.show()
