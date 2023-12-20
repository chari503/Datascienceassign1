import pandas as pd
import matplotlib.pyplot as plt

# Load the cleaned dataset
cleaned_csv_filename = 'cleaned_dataset.csv'
df = pd.read_csv(cleaned_csv_filename)

# Assuming the dataset has a "Category" and "Value" column
category_column = 'Category'
value_column = 'Value'

# Group the data by category and calculate the mean value for each category
mean_values = df.groupby(category_column)[value_column].mean()

# Plotting a bar chart
plt.figure(figsize=(10, 6))
mean_values.plot(kind='bar', color='skyblue')
plt.title('Mean Value by Category')
plt.xlabel(category_column)
plt.ylabel('Mean ' + value_column)
plt.xticks(rotation=45, ha='right')
plt.tight_layout()

# Display the plot
plt.show()

