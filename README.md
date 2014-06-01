<center><img src="https://jfqcza.bn1.livefilestore.com/y2paqP_3uagi8J3WlP4-pNt4kJoOzRKmuohSQUsrjaegIaoNbNZJ7EXLEflIO6XYAOKM6scpKxbtXPg10RL5OO3A9bc6m-zERVRHUYB1OEGq8s/Concur_Logo_VT_Color_500px.png?psid=1" width="190px" /></center>

What is Concur?
--

Concur is a travel and expense software solution that lets 25M business travelers book their travel, capture expense, submit expense reports, and more.  Concur processes over 55 million transactions every year, representing $50 billion spend on T&E.

<center>
<img src="https://jfqcza.bn1.livefilestore.com/y2prf7yXWtqtcsjpFh2XXu6XQ7ppeIg8SqyBAFEUIcqwGG-TQz1vpZhxx6ac2ySbguL5EAsg0IerEzlUQRynANwyVmyt9dUxWWwNS-x75NX248/Screen%20Shot%202014-05-31%20at%2012.02.06%20PM.png?psid=1" /></center>

What can I do with Concur APIs?
--

The Travel/Itinerary API (v1.1) lets you access a Concur user's itinerary, including hotel/flight booking info.  As an example, you can mash-up the Itinerary API with a restaurant database/API to provide recommendations of places to eat near a COncur user's hotel booking.

The Expense API (v3.0) allows you to get (and push) a Concur user's expense information, including expense line items, their types (e.g. food, lodging), totals, and even receipt images.

Here's an example on how to get an Itinerary List of a Concur user:

    curl https://www.concursolutions.com/api/travel/trip/v1.1
    -H "Authorization: OAuth <insert your access token here>"
    
To get an expense summary by using the Expense Report Digest API:

    curl https://www.concursolutions.com/api/v3.0/expense/reportdigests
    -H "Authorization: OAuth <insert your access token here>"
    -H "Accept: application/json"
    
**To get an access token** (or learn how to generate one), please go to the Concur booth or click [here]() to advance to the section below.

You can interact with the API using Swagger [here](https://www.concursolutions.com/api/docs/index.html)

<a href="https://www.concursolutions.com/api/docs/index.html"><img src="https://jfqcza.bn1.livefilestore.com/y2phbDjCiRKZp3Btneho4UncjWK46iv8GFhyKdTZ7xJJ9BCJ-JJiNrw7ieCenHdSGPgEZL0Tj7IYjGypUv61u3KdIrjj0dAUM35DjC3cPzLls0/Screen%20Shot%202014-05-31%20at%202.09.43%20PM.png?psid=1" width="610px" /></a>

For the Itinerary APIs (v1.1), full API documentation, and apps that use the APIs, please refer to:

[https://developer.concur.com/get-started/webservices-overview](https://developer.concur.com/get-started/webservices-overview)

Ideas for a Concur-powered business travel app:
--

<img src="https://jfqcza.bn1.livefilestore.com/y2pW4OEzxTpguO8XL5IAIzNQ_CiRQbSVAYOnWeNd1IWvId3XAfM0jIy9OTT0UgbaIjdepBO1JjbtmXP7JU3J_tO1JkNh1UbcmbE_HElMGRvXoQ/Wearable%20World%20-%20AA%20Hack%20map.png?psid=1" width="610px"/>
(Image above:  Floor plan of Wearable Travel Hackathon - Parking, Checkin, Security, Gate, Club)

Mash-up  | Idea
------------- | -------------
**Concur + smartwatch/ring**  | Use smartwatch/ring to confirm if Mastercard purchase line item should be sent to Concur as expense (or ignored if personal purchase); Display QR code to POS reader to send purchase as expense to Concur
**Concur + beacons/indoor position**  | Use Concur user's expense history to push relevant proximity ads/recommendations; Determine walk-time to gate based on Itinerary info
**Concur + credit/debit card**  | Use smartwatch/ring to confirm if Mastercard purchase line item should be sent to Concur as expense (or ignored if personal purchase)
**Concur + parking** | User Concur itinerary info (hotel/flight booking) to find fastest route to parking
**Concur + wifi service** | Identify if colleagues are on same flight and initiate chat session

Incentives
--

- To be announced

