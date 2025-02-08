# NextAuth Session Undefined in Next.js 15

This repository demonstrates a bug where the NextAuth session is undefined in a Next.js 15 application after a successful login.  The issue occurs specifically on the server-side, while client-side rendering works correctly.

## Bug Description

The `session` object returned by `unstable_getServerSession` is `undefined` even though the user successfully logs in. This leads to errors when attempting to access session properties server-side, causing the app to misbehave or crash on the server.

## Reproduction

1. Clone this repository.
2. Install dependencies: `npm install`
3. Run the development server: `npm run dev`
4. Log in using the provided authentication method (e.g., email/password).
5. Observe that the `/about` page renders correctly client-side, but server-side rendering fails due to the undefined session.

## Solution

The solution involves correctly configuring NextAuth and ensuring proper handling of the session object in the `getServerSideProps` or `getStaticProps` functions (if used). See `aboutSolution.js` for an example fix.
