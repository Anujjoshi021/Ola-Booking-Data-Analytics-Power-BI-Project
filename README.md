# Ola-Booking-Data-Analytics-Power-BI-Project
The objective of this project is to analyze Ola’s revenue and operational data for July 2024 to:

➤ Understand payment method preferences and their impact on total revenue.

➤ Identify high-value customers and analyze their contribution.

➤ Examine daily ride distances to track demand consistency.

➤ Provide data-driven recommendations to optimize payment strategies and customer engagement.

This analysis aims to uncover actionable business insights to improve financial performance and enhance operational efficiency.
<h1>Data-Backed Insights & Conclusions:</h1>
<img src = "https://github.com/Anujjoshi021/Ola-Booking-Data-Analytics-Power-BI-Project/blob/main/Snapshots%20of%20the%20Dashboard_/Overall.png">
<h2>📊 Ride Volume Breakdown by Status</h2>

✅ <strong>Successful Bookings:</strong> 63.97K rides were completed successfully, representing ~62.09% of total bookings.

❌ <strong>Cancellations:</strong>

Canceled by Customer: 18.43K (~17.89%)

Canceled by Driver: 10.5K (~10.19%)

Driver Not Found: 10.12K (~9.83%)</br></br>

➤ <strong>Insight:</strong> Around 38% of the bookings failed due to either cancellations or driver unavailability. This is a significant number that impacts both customer experience and business revenue.

<h3>🧠 Actionable Insights:</h3>
➤ High Cancellation Rate: Over 1 in 3 rides are unsuccessful – efforts should focus on reducing both driver and customer cancellations.</br></br>

➤ Driver Allocation Issue: ~10% of rides show "Driver Not Found" — this suggests inefficiencies in fleet management or driver availability.

➤ Revenue Opportunity: Improving the success rate could significantly increase revenue beyond the current ₹35M monthly value.</br></br></br></br>


<img src = "https://github.com/Anujjoshi021/Ola-Booking-Data-Analytics-Power-BI-Project/blob/main/Snapshots%20of%20the%20Dashboard_/Cancellation.png">

<h2>📊 Booking Overview:</h2>
Total Bookings: 1,03,024 </br></br>

Successful Bookings: 63,967

Cancelled Bookings: 28,933

Cancellation Rate: ~28.08%</br></br>

➤ <strong>Insight:</strong> Nearly 1 in every 4 rides was cancelled — a significant loss of revenue and customer trust. Root causes must be identified and resolved to reduce churn.</br></br></br></br>

<img src = "https://github.com/Anujjoshi021/Ola-Booking-Data-Analytics-Power-BI-Project/blob/main/Snapshots%20of%20the%20Dashboard_/Revenue.png">
<h2>✅ Key Insights:</h2>
Cash (≈50%) dominates Ola’s revenue collection.

UPI (≈38%) follows, showing strong digital adoption.

➤ Card payments are underutilized (<10% combined), suggesting opportunity for incentivization (e.g., cashback or discounts) to promote non-cash methods.

➤ Top 5 customers alone contributed ~₹32.6K, indicating a small but high-value customer segment. These users may benefit from premium loyalty programs, referral incentives, or targeted offers to retain and expand spending. </br></br></br></br>






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





