# Creating an instagram access token the quick and dirty way no code required

1. add a new client at [instgram.com/developers](https://www.instagram.com/developer/clients/manage/) add a redirect url of any page on your website and make a note of it, along with the client id, both will be used in the next step
2. in your browser visit https://www.instagram.com/oauth/authorize/?client_id=CLIENT_ID&redirect_uri=REDIRECT_URL&response_type=token&scope=public_content replacing CLIENT_ID and REDIRECT_URL with the values from the new client you just added
3. You should now be at an instragram page asking you to auth the app, confirm it
4. You'll have been redirected back to your website, click in the address bar and you'll see your access token e.g. **REDIRECT_URL**#access_token=**ACCESS_TOKEN** copy the token and use in api calls to instagram

## example

having added a a new client with a redirect url of https://www.myapp.com and got a client id of abcdefabcdefabcdefabcdefabcdef
Enter the following URL in your browser

https://www.instagram.com/oauth/authorize/?client_id=abcdefabcdefabcdefabcdefabcdef&redirect_uri=https://www.myapp.com&response_type=token&scope=public_content

Approve the apps access, and you'll get redirected to a url of

https://www.myapp.com#access_token=1234567.ab12345.1234567ab1234567ab1234567ab12345

copy the access_token from the URL in the browsers URL bar and now your set to access the instragram API

e.g. get the users recent media with

https://api.instagram.com/v1/users/self/media/recent?access_token=1234567.ab12345.1234567ab1234567ab1234567ab12345
