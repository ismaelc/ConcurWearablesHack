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
**Concur + weather** | Predict weather using Concur traveler's destination and date
**Concur + smartwatch/ring**  | Use smartwatch/ring to confirm if Mastercard purchase line item should be sent to Concur as expense (or ignored if personal purchase); Display QR code to POS reader to send purchase as expense to Concur
**Concur + beacons/indoor position**  | Use Concur user's expense history to push relevant proximity ads/recommendations; Determine walk-time to gate based on Itinerary info
**Concur + credit/debit card**  | Use smartwatch/ring to confirm if Mastercard purchase line item should be sent to Concur as expense (or ignored if personal purchase)
**Concur + parking** | User Concur itinerary info (hotel/flight booking) to find fastest route to parking
**Concur + wifi service** | Identify if colleagues are on same flight and initiate chat session

Incentives
--

- **$500 Amazon gift card** to winning team for the **"Best Use of Concur APIs"**
- **1-year free access to [TripIt Pro](https://www.tripit.com/pro/comparison)** (10 promo cards to give away) 

Additional Information
--
The subsections below provide a more detailed information on how to:

  - [Generate an access token](#token)


 <a name="token">**Generate an access token**</a>
 --

  1. **Get your Consumer Key**  

 After logging in to http://concursolutions.com, go to Administration -> Register Partner Application -> Concur Partner Application (Modify).  We need the consumer key so we can call the endpoint that would return the access token.

  <img src='http://chrispogeek.files.wordpress.com/2014/01/untitled.png' width="600px" />

  2.  **Call the endpoint to request an access token**

  Here's what the HTTP call looks like to request for an access token:

        GET https://www.concursolutions.com/net2/oauth2/accesstoken.ashx HTTP 1.1
        Authorization: Basic am9obl9kZXZlbG90bWFpbC5jb206VHJhdmVsJkV4cGVuc2UkMjAxMg==
        X-ConsumerKey: eZByXv2X41cJlC21pSVvRi    

  Note that we already have `X-ConsumerKey` from number 1.  To generate the `Authorization: Basic` value, you need to Base64-encode the login ID, colon and password such that john_developer@hotmail.com:Travel&Expense$2012 becomes am9obl9kZXZlbG90bWFpbC5jb206VHJhdmVsJkV4cGVuc2UkMjAxMg==.  If you're not doing this programmatically yet, you can use this [nifty web tool](http://www.base64encode.org/) to generate that value (remember to choose Encode).

  If you're using a Terminal, an equivalent curl statement of the above would be:
        
        curl https://www.concursolutions.com/net2/oauth2/accesstoken.ashx
        -H "Authorization: Basic am9obl9kZXZlbG90bWFpbC5jb206VHJhdmVsJkV4cGVuc2UkMjAxMg=="
        -H "X-ConsumerKey: eZByXv2X41cJlC21pSVvRi"

  If the call is successful, you should get an XML response with a `<Token>` node.  That's your access token. We recommend that you use [Postman](http://www.getpostman.com/), a Chrome extension, to help you manage your API calls (not just Concur ones).  Here's what the API calls look like in Postman:

  <img src='http://chrispogeek.files.wordpress.com/2014/01/screen-shot-2014-01-13-at-4-45-35-pm.png' width="600px" />

  *Chris has already built a couple of Concur Postman "Collections", email him at chris.ismael@concur.com if you want to get it.*

  3.  **Call the APIs to pull expense report items**

 After getting an access token, we can pull dummy data from the Expense Report Digest, like so (in Terminal):

        curl https://www.concursolutions.com/api/v3.0/expense/reportdigests
        -H "Authorization: OAuth <insert your access token here>"
 
  This would return an Expense Report response, with a field called `ID`.  We need this ID to extract the expense line items we created in the app earlier.  To liven things up a bit, let's use the [Swagger](https://www.concursolutions.com/api/docs/index.html#!/Entries) documentation of the "Entries" API to get the individual expense line items:

  <img src='https://jfqcza.bn1302.livefilestore.com/y2pExFhXefF7BWcggCWbeRkUyOUyEf1UdRi0HoCcpj8PKfaGMub-K8xc0BXHsX2NUFlNp54-m6X3aJ7dRNLQiIHfyYJhdtTiEJEArnZJ-r7NCA/Screen%20Shot%202014-04-22%20at%201.21.55%20PM.png?psid=1' width="600px" />

  We highlighted two things here, the (oval) field where you put in your access token, and the (rectangle) field where you put in the `ID` we got from the previous API call.  Note that we can do this same call in curl, or in any fashion you want.  Swagger just provides us a consolidated way to make the API calls.

  To execute the call, click the "Try it out!" button.  You should get a response like this below:

  <img src='https://jfqcza.bn1304.livefilestore.com/y2pty6lMBv5XXLjA_mT5HLpSNea4hVr3AUCRuEI207Wr1otLVxy86klHYuNDP0N-cvb75IFJvicR1jR2K7X3wqJXsH_AQNcEWkp6iO4t3jXRCs/Screen%20Shot%202014-04-22%20at%201.29.22%20PM.png?psid=1' width="600px" />

[Back to Top](#top)

