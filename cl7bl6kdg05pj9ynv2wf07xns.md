## Add Google Authentication to your NextJs project using NextAuth.js

Next-Auth is a complete open-source authentication for [Next.Js](https://nextjs.org/) applications. You can learn more about it [here](https://next-auth.js.org/).

Here in this blog tutorial, I will show you how you can use [NextAuth.js](https://next-auth.js.org/) in your NextJs project to add Google authentication. In this particular tutorial I am using `Typescript` but you can follow it for `Javascript`.

## Installation
You can install it using yarn or using npm.
```
yarn add next-auth
```
```
npm install next-auth
```

## Adding api routes
To add NextAuth.js in your project you need to first create `[...nextauth].ts` inside you `pages/api/auth`.


```typescript
// pages/api/auth/[...nextauth].ts

import NextAuth, { NextAuthOptions } from 'next-auth'
import GoogleProvider from 'next-auth/providers/google'

export const authOptions: NextAuthOptions = {
	providers: [
		GoogleProvider({
			clientId: process.env.GOOGLE_CLIENT_ID, // 'Your Google Client ID'
			clientSecret: process.env.GOOGLE_CLIENT_SECRET, //  'Your Google Client SECRET'
		}),
		// you can add more providers here
	],
}

export default NextAuth(authOptions)
```


## Grab your keys from Google Cloud
[Click here](https://console.cloud.google.com/apis/dashboard) and setup you app

Step 1: Create a project with any name you want.
Step 2: Go to Credentials tab ![Credentials tab on google api cloud](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/wzpq57495ab4k33sepcg.png)
Step 3: Create credentials ![Creating Credentials](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/lzrik5zqxq43vvvnj5g4.png)
Step 4: Choose OAuth client ID option ![OAuth client ID option](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/sux8tcz7ciqj5vevav8h.png)
Step 5: Fill some details to get you google client Id and Secret ![Filling Details](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/45509qlzwxbk7e24lwaw.png)

Step 6: After you press create button, You will get you google client id and google client secret. Save these credentials in your pc. ![Google Client id and secret](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/6vy3faogbothb80vlzfs.png)

## Setting up environment variables
Create a `.env.local` file inside you root directory.
```
GOOGLE_CLIENT_ID="Paste your google client ID here"
GOOGLE_CLIENT_SECRET="Paste you google client secret here"
```

## Setting up OAuth inside our app
To be able to use `useSession` inside your app, you'll first need to wrap your top level component inside `<SessionProvider></SessionProvider>` which is coming from `next-auth/react`

```typescript
// _app.tsx

import '../styles/globals.css'
import type { AppProps } from 'next/app'
import { SessionProvider } from 'next-auth/react'

function MyApp({ Component, pageProps: { session, ...pageProps } }: AppProps) {
	return (
		<SessionProvider session={session}>
			<Component {...pageProps} />
		</SessionProvider>
	)
}

export default MyApp
```
Now we are good to go.

## Using Google Authentication in our app
To use authentication, we need to import some functions from `next-auth/react`

```typescript
import { useSession, signIn, signOut } from 'next-auth/react'
```

Now, inside our components we can use `useSession`, `signin` and `signout` functions
```typescript

export const MyComponent = () => {
  const { data: session } = useSession()
	
	//... Your code

	return (
		<>
			{/* Your Code */}

			{session ? (
					<>
						<h2>
							Signed in as {session.user.email}
						</h2>
						<button	onClick={() => signOut()}>
							Sign out
						</button>
					</>
				) : (
					<button onClick={() => signIn()}>
						Login With Google
					</button>
				)}
				

			{/* Your Code */}
		</>
	)
}
```


## Congratulations 🎉🎉🎉
You have successfully added NextAuth.js in your project for Google Authentication.

## Full source code
you can see the full code on GitHub - [Link](https://github.com/shubhamku044/next-auth-google)

### Thank you for reading my article.
For any query you can directly reach out to me on [Twitter](https://twitter.com/shubhamku044) or [LinkedIn](https://www.linkedin.com/in/shubhamku044/)
 