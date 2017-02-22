# Response Codes

Different methods have different possible response codes. Here is a summary of all of the response codes the Crystal API uses:

Code | Meaning
---------- | -------
200 | Success -- Not an error, just happy things
400 | Missing Valid Param -- Check parameters for errors
401 | Key Was Invalid -- Your API key is wrong
403 | Forbidden -- You are not authorized to access this content
404 | Not Found -- Double check your search queries
418 | I'm a teapot -- [Or coffee pot](https://en.wikipedia.org/wiki/Hyper_Text_Coffee_Pot_Control_Protocol)
500 | Internal Server Error -- We had a problem with our server. Try again later.
503 | Service Unavailable -- We're temporarily offline for maintenance. Please try again later.
