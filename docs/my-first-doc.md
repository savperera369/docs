---
sidebar_position: 2
---

# Project Setup Guide

- Unzip the folder and open it in an IDE of your choice
- Run the command npm install to install all necessary dependencies
- Create a .env file in the root of the project directory
- Add this api key to the .env file COINCAP_API_KEY='80dfec98-d773-4fa2-ba8c-b9331a8731f6'
- Run the command npm run dev to start the application

## API Integration Details

In the provided code, data is fetched from the CoinCap API using the fetchCryptoData function, 
which makes a GET request to retrieve cryptocurrency data. The response object returns an array of all cryptocurrencies, so only
the first 5 are kept using the JavaScript slice function. This function is triggered by the useQuery hook from @tanstack/react-query, which manages the data fetching, loading, error states, and caching. The fetched data is then filtered based on the user's searchTerm input, and formatted using helper functions. The refetch function allows the user to manually trigger a data refresh. The UI conditionally renders either a loading state, an error message, or the fetched and filtered data, 
displaying it in either a table or a condensed view depending on the tableView state.

## State Management Explanation

The state manager I used was React Query. React Query was a good choice for state management in this application because it simplifies data fetching, caching, and synchronization. 
It handles the complexity of managing loading, error, and success states automatically, reducing boilerplate code. The useQuery hook efficiently fetches the cryptocurrency data, 
caches it, and provides built-in features like automatic retries and background refetching. React Query also ensures that the data is fresh by enabling manual refetching via the refetch function, 
making it ideal for managing remote data. This allows the app to focus on UI rendering and logic, while React Query handles the underlying data management seamlessly.

## Challenges and Solutions Faced 

One of the main challenges I faced while building this project was ensuring smooth data fetching and state management. Initially, managing the data fetching manually and handling loading, error, and success states felt cumbersome. 
I solved this by using React Query, which streamlined the process, providing automatic caching, background refetching, and an easy-to-use API for managing remote data. 
Another challenge was integrating the CoinCap API and ensuring that the fetched data was displayed correctly in the dashboard, especially when dealing with formatting and filtering the data. 
To address this, I created helper functions to format the data, such as converting large numbers and percentages into more readable formats. The last challenge was designing the UI to be intuitive, especially with the search bar and "Refresh" button for manual updates. 
I ensured that the UI remained responsive and user-friendly by using Tailwind CSS for styling and testing different layouts. Additionally, creating the developer documentation in Docusaurus was a bit tricky at first, but the clear setup guide and built-in markdown support made it manageable.



