Q1. Name any five plots that we can plot using the Seaborn library. Also, state the uses of each plot.
Scatter Plot:

Use: To visualize the relationship between two continuous variables. It helps in identifying correlations, patterns, and outliers in the data.
python
Copy code
import seaborn as sns
sns.scatterplot(x='variable1', y='variable2', data=dataset)
Line Plot:

Use: To display data points connected by straight lines. It's useful for time series data and for understanding trends over a continuous variable.
python
Copy code
sns.lineplot(x='time', y='value', data=dataset)
Box Plot:

Use: To show the distribution of a dataset based on a five-number summary (minimum, first quartile, median, third quartile, and maximum). It highlights outliers and variations between different groups.
python
Copy code
sns.boxplot(x='category', y='value', data=dataset)
Histogram:

Use: To represent the distribution of a single continuous variable by dividing the data into bins and counting the number of observations in each bin.
python
Copy code
sns.histplot(data=dataset, x='value')
Heatmap:

Use: To display the magnitude of values as color in a two-dimensional map. It's useful for visualizing matrix-like data, such as correlation matrices.
python
Copy code
sns.heatmap(data=matrix_data)
Q2. Load the "fmri" dataset using the load_dataset function of seaborn. Plot a line plot using x = "timepoint" and y = "signal" for different events and regions.
python
Copy code
import seaborn as sns
import matplotlib.pyplot as plt

# Load the dataset
fmri = sns.load_dataset('fmri')

# Plot the line plot
sns.lineplot(x='timepoint', y='signal', hue='event', style='region', data=fmri)
plt.title('FMRI Signal Over Time by Event and Region')
plt.show()
Q3. Load the "titanic" dataset using the load_dataset function of seaborn. Plot two box plots using x = 'pclass', y = 'age' and y = 'fare'.
python
Copy code
import seaborn as sns
import matplotlib.pyplot as plt

# Load the dataset
titanic = sns.load_dataset('titanic')

# Plot the box plots
plt.figure(figsize=(14, 6))

plt.subplot(1, 2, 1)
sns.boxplot(x='pclass', y='age', data=titanic)
plt.title('Box Plot of Age by Passenger Class')

plt.subplot(1, 2, 2)
sns.boxplot(x='pclass', y='fare', data=titanic)
plt.title('Box Plot of Fare by Passenger Class')

plt.tight_layout()
plt.show()
Q4. Use the "diamonds" dataset from seaborn to plot a histogram for the 'price' column. Use the hue parameter for the 'cut' column of the diamonds dataset.
python
Copy code
import seaborn as sns
import matplotlib.pyplot as plt

# Load the dataset
diamonds = sns.load_dataset('diamonds')

# Plot the histogram
sns.histplot(data=diamonds, x='price', hue='cut', multiple='stack')
plt.title('Histogram of Diamond Prices by Cut')
plt.show()
Q5. Use the "iris" dataset from seaborn to plot a pair plot. Use the hue parameter for the "species" column of the iris dataset.
python
Copy code
import seaborn as sns
import matplotlib.pyplot as plt

# Load the dataset
iris = sns.load_dataset('iris')

# Plot the pair plot
sns.pairplot(iris, hue='species')
plt.suptitle('Pair Plot of Iris Dataset', y=1.02)
plt.show()
Q6. Use the "flights" dataset from seaborn to plot a heatmap.
python
Copy code
import seaborn as sns
import matplotlib.pyplot as plt

# Load the dataset
flights = sns.load_dataset('flights')

# Pivot the data
flights_pivot = flights.pivot('month', 'year', 'passengers')

# Plot the heatmap
sns.heatmap(flights_pivot, annot=True, fmt='d', cmap='YlGnBu')
plt.title('Heatmap of Flight Passengers')
plt.show()
