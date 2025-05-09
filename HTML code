# Import libraries
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

# Set style
sns.set(style="whitegrid")

# Load dataset
df = pd.read_csv("data/tourism_data.csv")  # Replace with actual file name

# Basic exploration
print("Dataset Info:")
print(df.info())
print("\nMissing values:\n", df.isnull().sum())

# Clean data (example: fill missing values)
df.fillna(method='ffill', inplace=True)

# Summary statistics
print("\nDescriptive Statistics:\n", df.describe())

# EDA: Tourist Arrivals Over Time
plt.figure(figsize=(12, 6))
sns.lineplot(data=df, x='Year', y='Arrivals', hue='Country')
plt.title("Tourist Arrivals Over Years by Country")
plt.xlabel("Year")
plt.ylabel("Number of Arrivals (Millions)")
plt.legend(bbox_to_anchor=(1.05, 1), loc='upper left')
plt.tight_layout()
plt.savefig("plots/tourist_arrivals_by_year.png")
plt.show()

# EDA: Top 10 Countries in Most Recent Year
latest_year = df['Year'].max()
top_countries = df[df['Year'] == latest_year].nlargest(10, 'Arrivals')

plt.figure(figsize=(10, 6))
sns.barplot(data=top_countries, x='Arrivals', y='Country', palette='viridis')
plt.title(f"Top 10 Tourist Destinations in {latest_year}")
plt.xlabel("Arrivals (Millions)")
plt.ylabel("Country")
plt.tight_layout()
plt.savefig("plots/top_10_destinations.png")
plt.show()
