# Unhandled Promise Rejection in Next.js 15 App

This repository demonstrates an uncommon bug in Next.js 15 applications where unhandled promise rejections can occur if a `fetch` call in a page component fails without proper error handling.  The `pages/about.js` component fetches data from an API route but doesn't handle potential network errors or the case where the API returns an error.  This leads to an unhandled promise rejection and a broken user experience.

## Bug Description

The primary issue is the lack of error handling in the `fetch` call within the `About` page component.  If the API request fails (e.g., network issues, server errors), the promise rejects, leading to an unhandled promise rejection. Additionally, there's no mechanism to gracefully handle this failure or display an appropriate message to the user.

## Solution

The solution involves using a `try...catch` block to handle potential errors during the `fetch` call and implementing conditional rendering to display appropriate content based on whether the data fetching succeeded or failed.