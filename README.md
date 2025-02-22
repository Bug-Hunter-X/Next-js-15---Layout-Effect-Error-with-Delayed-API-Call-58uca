# Next.js 15 - Layout Effect Error with Delayed API Call

This repository demonstrates a bug in a Next.js 15 application where a delayed API call in a route causes a "Layout effect cannot be performed during the initial render" error.  The About page shows a loading message, but the data never updates after the API call completes.  The solution shows how to properly handle asynchronous data fetching to avoid this issue.

## Bug Reproduction

1. Clone this repository.
2. Run `npm install`.
3. Run `npm run dev`.
4. Navigate to `/about`.
5. Observe that the page displays "Loading..." indefinitely, despite the API call successfully returning data.

## Bug Solution

The issue arises from trying to perform an action in useEffect within the initial render of the component before data is fetched. The solution is to conditionally render or perform the data update only after the initial data fetching.