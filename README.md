# Ola-Booking-Data-Analytics-Power-BI-Project

<h2>Power BI Questions:</h2>
1. Ride Volume Over Time <br/>
2. Booking Status Breakdown <br/>
3. Top 5 Vehicle Types by Ride Distance  <br/>
4. Average Customer Ratings by Vehicle Type  <br/>
5. cancelled Rides Reasons  <br/>
6. Revenue by Payment Method  <br/>
7. Top 5 Customers by Total Booking Value  <br/>
8. Ride Distance Distribution Per Day  <br/>
9. Driver Ratings Distribution  <br/>
10. Customer vs. Driver Ratings  <br/>


<h2>Power BI Answers:</h2>
<h3>Segregation of the views:</h3>
<h4>1. Overall</h4>
- Ride Volume Over Time <br/>
- Booking Status Breakdown <be/>
<h4>2. Vehicle Type</h4>
- Top 5 Vehicle Types by Ride Distance <br/>
<h4>3. Revenue</h4>
- Revenue by Payment Method <br/>
- Top 5 Customers by Total Booking Value <br/>
- Ride Distance Distribution Per Day <br/>
<h4>4. Cancellation</h4>
- Cancelled Rides Reasons (Customer) <br/>
- cancelled Rides Reasons(Drivers) <br/>
<h4>5. Ratings</h4>
- Driver Ratings <br/>
- Customer Ratings <br/>

<h2>Answers:</h2>
<strong>1. Ride Volume Over Time:</strong> A time-series chart showing the number of rides per day/week. <br/> <br/>
<strong>2. Booking Status Breakdown:</strong> A pie or doughnut chart displaying the proportion of different
booking statuses (success, cancelled by the customer, cancelled by the driver, etc.). <br/> <br/>
<strong>3. Top 5 Vehicle Types by Ride Distance:</strong> A bar chart ranking vehicle types based on the total
distance covered. <br/><br/>
<strong>4. Average Customer Ratings by Vehicle Type:</strong> A column chart showing the average
customer ratings for different vehicle types. <br/> <br/>
<strong>5. cancelled Rides Reasons:</strong> A bar chart that highlights the common reasons for ride
cancellations by customers and drivers. <br/> <br/>
<strong>6. Revenue by Payment Method:</strong> A stacked bar chart displaying total revenue based on
payment methods (Cash, UPI, Credit Card, etc.). <br/> <br/>
<strong>7. Top 5 Customers by Total Booking Value:</strong> A leaderboard visual listing customers who have
spent the most on bookings. <br/> <br/>
<strong>8. Ride Distance Distribution Per Day:</strong> A histogram or scatter plot showing the distribution of
ride distances for different Dates. <br/> <br/>
<strong>9. Driver Rating Distribution:</strong> A box plot visualizing the spread of driver ratings for different
vehicle types. <br/> <br/>
10. Customer vs. Driver Ratings: A scatter plot comparing customer and driver ratings for
each completed ride, analyzing correlations. <br/> <br/>


<h2>SQL Questions:</h2> 
1. Retrieve all successful bookings: <br/>
2. Find the average ride distance for each vehicle type: <br/>
3. Get the total number of cancelled rides by customers:<br/>
4. List the top 5 customers who booked the highest number of rides: <br/>
5. Get the number of rides cancelled by drivers due to personal and car-related issues: <br/>
6. Find the maximum and minimum driver ratings for Prime Sedan bookings: <br/>
7. Retrieve all rides where payment was made using UPI: <br/>
8. Find the average customer rating per vehicle type: <br/>
9. Calculate the total booking value of rides completed successfully: <br/>
10. List all incomplete rides along with the reason: <br/>


<h2>SQL Questions & Answers</h2>
Create Database Ola; <br/>
Use Ola; <br/> <br/>
<strong>#1. Retrieve all successful bookings:</strong> <br/>
Create View Successful_Bookings As <br/>
SELECT * FROM bookings <br/>
WHERE Booking_Status = 'Success'; <br/> <br/>
<strong>#2. Find the average ride distance for each vehicle type:</strong> <br/>
Create View ride_distance_for_each_vehicle As <br/>
SELECT Vehicle_Type, AVG(Ride_Distance) <br/>
as avg_distance FROM bookings <br/>
GROUP BY Vehicle_Type; <br/> <br/>
<strong>#3. Get the total number of cancelled rides by customers:</strong>strong> <br/>
Create View cancelled_rides_by_customers As <br/>
SELECT COUNT(*) FROM bookings <br/>
WHERE Booking_Status = 'cancelled by Customer'; <br/> <br/>
<strong>#4. List the top 5 customers who booked the highest number of rides:</strong> <br/>
Create View Top_5_Customers As <br/>
SELECT Customer_ID, COUNT(Booking_ID) as total_rides <br/>
FROM bookings <br/>
GROUP BY Customer_ID <br/>
ORDER BY total_rides DESC LIMIT 5; <br/> <br/>
<strong>#5. Get the number of rides cancelled by drivers due to personal and car-related issues:</strong>
Create View Rides_cancelled_by_Drivers_P_C_Issues As<br/>
SELECT COUNT(*) FROM bookings<br/>
WHERE cancelled_Rides_by_Driver = 'Personal & Car related issue';<br/><br/>
<strong>#6. Find the maximum and minimum driver ratings for Prime Sedan bookings:</strong>
Create View Max_Min_Driver_Rating As<br/>
SELECT MAX(Driver_Ratings) as max_rating,<br/>
MIN(Driver_Ratings) as min_rating<br/>
FROM bookings WHERE Vehicle_Type = 'Prime Sedan';<br/><br/>
<strong>#7. Retrieve all rides where payment was made using UPI:</strong><br/>
Create View UPI_Payment As<br/>
SELECT * FROM bookings<br/>
WHERE Payment_Method = 'UPI';<br/><br/>
<strong>#8. Find the average customer rating per vehicle type:</strong>
Create View AVG_Cust_Rating As<br/>
SELECT Vehicle_Type, AVG(Customer_Rating) as avg_customer_rating<br/>
FROM bookings<br/>
GROUP BY Vehicle_Type;<br/><br/>
<strong>#9. Calculate the total booking value of rides completed successfully:</strong>
Create View total_successful_ride_value As<br/>
SELECT SUM(Booking_Value) as total_successful_ride_value<br/>
FROM bookings<br/>
WHERE Booking_Status = 'Success';<br/><br/>
<strong>#10. List all incomplete rides along with the reason:</strong>
Create View Incomplete_Rides_Reason As<br/>
SELECT Booking_ID, Incomplete_Rides_Reason<br/>
FROM bookings<br/>
WHERE Incomplete_Rides = 'Yes';<br/>





