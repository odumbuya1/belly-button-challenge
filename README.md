# belly-button-challenge

OVerview:
An interactive dashboard is built to examine the the Belly Burton Biodiversity Dataset with information about microbes affecting human navels. The dashboard shows an interactive visuals of the following:
- Horizontal bar chart with a dropdown menu to display the top 10 OTUs;
- A bubble chart of x and y values with varying bubble sizes;
- Individual's demographic information showing sample metadata;
- A drop down of "Test subject ID numbers" and
- A weekly belly burton wash frequency.
The "Belly Burton Diversity Dashboard" captures all the above interactive visuals. See below for the guide to the steps or methods.

Step 1.
* Create a metadata function  -- function buildMetadata(sample) { } --  from data requested from URL (...) using 'http get' declared as d3.json(). The metadata fuction is used for the following purposes:

  1. To examine, and determine an array of metadate object properties filtered for a common sample of microbial species or OTU  and other rare species. 
  2. Use d3.select() method to reference the 'id' for sample metadate assigned to a variable called PANEL, let PANEL.
  3. Use for loop to return key - value pairs  

Step 2.
The chart function declaration -- d3.json(...).then((data) => { ... })-- is used to identify specific sample from the URL: (...);and the then() block, received the data to build the charts. The relevant portions are as follows:

Bubble Chart:
Data:
otu_ids,otu_labels, and sample_values are used for x, y, and text values. The Bubble Chart visualizes the relationship between otu_ids, sample_values, and otu_labels. See code for bubbledata , layout and Plotly.newPlot("bubble", bubbleData, bubbleLayout) on file "plot.js"


Horizontal barcharts
The code prepares data and layout options for the Bar Chart (Plotly.newPlot("bar", barData, barLayout)).
It selects the top 10 entries based on otu_ids and sample_values, then creates a horizontal bar chart to display this information.

Summary:
The buildCharts(sample) function fetches data from an external JSON file.
It extracts specific data from the fetched JSON and uses Plotly to generate a Bubble Chart and a Bar Chart based on the received data. These charts likely display information related to the specified sample, such as bacterial cultures or other biological data.

