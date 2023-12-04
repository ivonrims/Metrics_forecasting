# Metrics forecasting

### Tools:
- Python
- ClickHouse
- Orbit

### Description 

The more active our users are, the higher the load on the servers. And lately we have been receiving more and more complaints that the application freezes. Sounds like a challenge for devops and engineers!

You were also asked to contribute to the task - to predict how user activity will change over the next month. Let's try to do this!

**Task:**

1) Select the main metric you plan to forecast. Justify why she is. What temporary permit will you take? Will there be any additional regressors that you will include in the model?

2) Build a model and validate it. Do we have enough data for backtesting with the current task? If not, then determine for what forecasting horizon we have enough data.

3) Choose the model that seems most successful to you (justify your choice). Interpret its results. If there are any important restrictions on the output, do not forget to indicate them too.

### Metric selection

**The total number of user actions** (HAU) was taken as the main metric - it is logical to assume that if the application freezes, then users will have problems performing this or that action - liking or even viewing a post. Moreover, if some users cannot access the application at all due to problems with the server, this will also be reflected in the number of likes and views. As a temporary resolution, we’ll take one **hour** (but here, you probably need to know how much the application freezes: if it’s some minor freezes when loading a page, then you can try to take the resolution for one second).

### Results

**Conclusion**: given that there are only 71 days of data for backtesting, it was decided to make a forecast for 2 weeks instead of a month. According to the forecast, in the next 14 days the number of user actions per hour will vary from 16,400 to 57,229 depending on the time of day and day of the week. Taking into account the confidence interval, the predicted values ​​can vary from 10,500 to 93,000 actions (depending on the time of day and day of the week). The forecast was also made on the assumption that repeated flash mobs and other events that could lead to a surge in activity are not expected in the next two weeks.
