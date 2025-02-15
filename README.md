# Matplotlib Basics: A Beginner's Guide to Data Visualization

## Introduction
Matplotlib is Python's most popular visualization library. Think of it as your digital drawing board where you can create anything from simple line plots to complex visualizations. Let's learn the basics with practical examples!

## The Basic Structure
Matplotlib has two main components:
1. `pyplot`: The main module we use (usually imported as `plt`)
2. `Figure` and `Axes`: Where we actually draw our plots

Here's your first plot:

```python
import matplotlib.pyplot as plt
import numpy as np

# Create some data
x = np.linspace(0, 10, 100)  # 100 points from 0 to 10
y = np.sin(x)

# Create the plot
plt.figure(figsize=(8, 4))  # Set figure size
plt.plot(x, y)
plt.title("My First Plot")
plt.xlabel("X axis")
plt.ylabel("Y axis")
plt.show()
```

## Common Plot Types

### 1. Line Plot
Perfect for showing trends over time:

```python
# Multiple lines on same plot
plt.figure(figsize=(10, 6))
plt.plot(x, np.sin(x), label='sin(x)')
plt.plot(x, np.cos(x), label='cos(x)')
plt.legend()  # Show the legend
plt.title('Sine and Cosine Waves')
plt.grid(True)  # Add grid
plt.show()
```

### 2. Scatter Plot
Great for showing relationships between variables:

```python
# Generate random data
data1 = np.random.normal(0, 1, 100)
data2 = np.random.normal(0, 1, 100)

plt.figure(figsize=(8, 6))
plt.scatter(data1, data2, alpha=0.5)  # alpha controls transparency
plt.title('Scatter Plot')
plt.xlabel('Variable 1')
plt.ylabel('Variable 2')
plt.show()
```

### 3. Bar Plot
Perfect for comparing categories:

```python
categories = ['A', 'B', 'C', 'D']
values = [23, 45, 56, 78]

plt.figure(figsize=(8, 6))
plt.bar(categories, values, color='skyblue')
plt.title('Simple Bar Chart')
plt.xlabel('Categories')
plt.ylabel('Values')
plt.show()
```

### 4. Histogram
For understanding data distribution:

```python
# Generate random data
data = np.random.normal(0, 1, 1000)

plt.figure(figsize=(8, 6))
plt.hist(data, bins=30, color='green', alpha=0.7)
plt.title('Histogram of Normal Distribution')
plt.xlabel('Value')
plt.ylabel('Frequency')
plt.show()
```

## Customization Tips

### 1. Subplots
Create multiple plots in one figure:

```python
# Create a figure with 2x2 subplots
fig, axes = plt.subplots(2, 2, figsize=(12, 8))

# Plot 1: Line plot
axes[0, 0].plot(x, np.sin(x))
axes[0, 0].set_title('Line Plot')

# Plot 2: Scatter plot
axes[0, 1].scatter(data1, data2, alpha=0.5)
axes[0, 1].set_title('Scatter Plot')

# Plot 3: Bar plot
axes[1, 0].bar(categories, values)
axes[1, 0].set_title('Bar Plot')

# Plot 4: Histogram
axes[1, 1].hist(data, bins=30)
axes[1, 1].set_title('Histogram')

plt.tight_layout()  # Adjust spacing between subplots
plt.show()
```

### 2. Styling Your Plots

```python
# Set style for better-looking plots
plt.style.use('seaborn')  # Try: 'ggplot', 'fivethirtyeight', 'bmh'

# Customize colors, markers, and line styles
plt.figure(figsize=(10, 6))
plt.plot(x, np.sin(x), 'r--', label='sin(x)')  # red dashed line
plt.plot(x, np.cos(x), 'b.-', label='cos(x)')  # blue line with dots
plt.title('Styled Plot', fontsize=14, fontweight='bold')
plt.legend(frameon=True, shadow=True)
plt.grid(True, linestyle='--', alpha=0.7)
plt.show()
```

## Pro Tips

1. Always use `plt.figure(figsize=(width, height))` to control plot size
2. Add labels and titles to make your plots self-explanatory
3. Use `plt.tight_layout()` when working with multiple subplots
4. Save your plots using:
   ```python
   plt.savefig('my_plot.png', dpi=300, bbox_inches='tight')
   ```

## Common Mistakes to Avoid

1. Forgetting to call `plt.show()`
2. Not clearing the plot between different visualizations (`plt.clf()`)
3. Overcrowding plots with too much information
4. Not setting appropriate figure sizes

Remember: The key to good visualization is clarity. Start simple, then add complexity as needed!
