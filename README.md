# IGC Relative Height Plot with Animation

This project provides a web application that reads IGC files, plots the relative height of flight data, and animates the plotting of this data point by point. The project uses Chart.js and the Chart.js Data Labels plugin.

## Features

- Upload and parse IGC files.
- Calculate and display relative heights based on the landing altitude.
- Display two plots:
  - A static plot showing all the data points.
  - An animated plot that adds data points one by one.
- Customize the animation by ignoring the first `n` seconds of data.
- Highlight the current point in the animated plot with a data label.

## Getting Started

### Prerequisites

To run this project, you need a web browser that supports HTML5 and JavaScript.

### Installing

Clone the repository or download the project files.

### Running the Application

1. Open the `index.html` file in a web browser.

2. Upload an IGC file using the file input.

3. (Optional) Specify the number of seconds to ignore at the beginning of the data.

4. The application will display two charts:
   - The upper chart shows the complete data.
   - The lower chart animates the data points one by one.

## Project Structure

- `index.html`: The main HTML file containing the structure of the web application.
- `README.md`: This readme file.

## Code Overview

### HTML Structure

The HTML file contains:
- An input for file upload.
- An input for specifying the number of seconds to ignore.
- Two canvas elements for displaying the charts.

### JavaScript

The JavaScript code:
- Reads and parses the IGC file.
- Calculates relative heights.
- Calculates time differences.
- Plots the complete data in a static chart.
- Animates the data points in a separate chart.

### Chart.js Configuration

The Chart.js configuration includes:
- Custom legend positioning.
- Data labels to display the current point in the animated chart.
- Padding inside the charts.

### Key JavaScript Functions

- `parseIGC(contents)`: Parses the IGC file content and extracts times and altitudes.
- `calculateRelativeHeight(altitudeData)`: Calculates the relative heights based on the landing altitude.
- `calculateTimeDiffs(times)`: Calculates the time differences between data points.
- `plotCompleteChart(times, data)`: Plots the complete data in a static chart.
- `animatePlot(times, data, timeDiffs)`: Animates the data points in a separate chart.

## Customization

### Adjust Margins Inside the Chart

To adjust the margins inside the chart, modify the `layout.padding` property in the Chart.js configuration:

```javascript
layout: {
  padding: {
    top: 20,
    right: 20,
    bottom: 20,
    left: 20
  }
}

