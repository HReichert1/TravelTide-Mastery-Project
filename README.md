# TravelTide-Mastery-Project
This project is about TravelTide customer data, that has to be segmented according to business needs and deliver data-driven recommendations based on your findings.

# Introduction
E-booking startup TravelTide is a new player in the online travel industry. It has experienced steady growth since it was founded at the tail end of the COVID-19 pandemic (2021-04) on the strength of its data aggregation and search technology, which is best in class. Certain aspects of the TravelTide customer experience are underdeveloped, resulting in poor customer retention. Now a marketing campaign should be designed and executed with personalized rewards program that keeps customers returning to the TravelTide platform. 
5 different perks have to be assigned to customers:
 - Free hotel meal
 - free checked bag
 - no cancellation fees
 - exclusive discounts
 - 1 night free hotel with flight

# Planning
1. Data exploration and finding groups which can be assigned for a perk
![image](https://github.com/user-attachments/assets/e5a58f3f-682f-4f2d-8704-d3c0ddc5c589)

2. Calculations and dat changes
   - re-calculation of the nights spent in a hotel without taking into consideration the time
     NULL values only for cancellation sessions nd hotel_booked = false
   - age: calculated base on birthdate and session_end
   - time_since_signup: calculated as difference between sign_up_date and session_end
   - duration_stay: calculated in hours either from return_time and departure_time or check_in_time and check_out_time
   - segment_family: calculated from married and has_children
     married, children
     not married, children
     married, no children
     not married, no children
   - add cancellation data to appropriate session_id
   - avg_days_to_cancellation using session_end of cancelled session and session_start
   - segment_cancellation:
     same-Day Cancellers
     Last-Minute Cancellers (1-7 days)
     Moderate Cancellers (8-30 days)
     Early Cancellers (30+ days)
   - avg_session_duration: difference of session_end and session_start
   - cost_flight: using base_fare_usd taking into consideration seats and flight_discount_amount
   - cost_hotel: using hotel_per_room_usd taking into consideration nights and hotel_discount_amount
   - avg_days_to_travel: difference of flight departure ot hotel check_in and session_end
   - travel_party: 100 --> group/family
                     1 --> solo
   - avg_distance_miles using longitude and latitude information of home and destination airport and applying the Harvesine formula
   -    
