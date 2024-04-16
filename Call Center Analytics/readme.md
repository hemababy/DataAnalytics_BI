## Dashboard Creation in Power BI

Create a comprehensive dashboard in Power BI to showcase relevant Key Performance Indicators (KPIs) and metrics from the dataset.
This dashboard aims to provide insights into the performance of the operations and help stakeholders make data-driven decisions.

### Data Transformation Steps:

1. **Changed Data Type:** 
   - Convert the data type for the columns "AvgTalkDuration" and "Time" to time format to facilitate further analysis.

### Key Performance Indicators (KPIs):

1. **Overall Customer Satisfaction:** Monitor the overall satisfaction rating of customers to ensure service quality.
   
2. **Overall Calls Answered/Abandoned:** Track the total number of calls answered and abandoned to assess call center efficiency.
   
3. **Calls answers per month:** Analyze call volume patterns throughout the month to identify peak hours and optimize staffing.
   
4. **Average Speed of Answer:** Measure the average time taken to answer calls, ensuring prompt customer service.
   
5. **Agent’s Performance Quadrant:** Evaluate agent performance based on average handle time (talk duration) vs. calls answered, categorizing agents into performance quadrants for targeted improvement strategies.

By visualizing these KPIs and metrics in a Power BI dashboard, stakeholders can gain valuable insights into call center performance and make informed decisions to enhance operational efficiency and customer satisfaction.

### Measures:
1. Avg_Time = AVERAGE(Sheet1[AvgTalkDuration])*24*60*60
2. Answered = CALCULATE(COUNT(Sheet1[Call Id]),FILTER(Sheet1, Sheet1[Answered (Y/N)]="Y"))
3. TotalCalls = [Answered] + [NotAnswered]
4. Resolved (Y) = CALCULATE(COUNT(Sheet1[Call Id]),FILTER(Sheet1,Sheet1[Resolved]="Y"))
5. NotAnswered = COUNTROWS(FILTER(Sheet1, Sheet1[Answered (Y/N)] = "N"))
6. CallAnswerRate = DIVIDE([Answered], [TotalCalls])
