# ReadMe

## 1. Crawler Function Detail

This crawler is made for guest users who have download limitation. This crawler for plastic waste trade data. However you can modify the API url for your own purpose.

### **get_countrycode()**

- To use UN Comtrade API we need country code.
- Get countries name and code as a JSON format.
- Extract country code and name and save as CSV.

### **auto_downloader(year)**

- Input:
> year: integer, multiple -> list format
- Request download data with extraction API.
- Check status code:
  > 200: Request Success 
  > 409: Usage Limit
- Restriction for guest users: 100 requests / hour
- Over 100 requests/hour -> time sleep(3600)
- Make ‘year_total.csv’ file for further analysis

## 2. Visualization Function Detail

Visualize the scraped dataset using bar chart, pie chart and line chart.

### **bar_chart(year, trade)**

- Input Values:
> year: integer, multiple -> list format
> trade: Import (1), Export (2)
- Plot with ‘year_total.csv’ file.

### **pie_chart(year, trade, rank)**

- Input Values:
> rank: integer (0~100), Ratio of trade Q’ty
- Plot with ‘year_total.csv’ file.

### **line_chart(trade, reporter)**

- Input Values: Refer to the ‘reporter.csv’
> reporter: string, multiple -> list format
- Yearly trade Q’ty change visualization of the country.
- Plot with ‘total_csv’ file.

## 3. Table Function Detail

Make tables with scraped dataset

### **changes_table(trade)**

- Input Values:
> trade: Import (1), Export (2)
- Analyze with ‘year_total.csv’ file.
- yearly plastic trade amount change.

### **rank_table(years, trade, top)**

- Input Values:
> years: string format, multiple -> list format
> top: Integer, Top ranked countries sorted by trade Q’ty
- Analyze with ‘total.csv’ file.
- yearly Top ranked importer or exporter