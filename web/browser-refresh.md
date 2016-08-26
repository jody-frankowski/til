# Browser Refresh

I knew that the behavior of a refresh in a browser usually depends on the
keys/buttons used. You can see comparisons [here](https://stackoverflow.com/questions/385367/what-requests-do-browsers-f5-and-ctrl-f5-refreshes-generate).
What I didn't understand was why I was seeing "304"s when refreshing the page
while clearly my browser (Firefox and Chromium show the same behavior) should
have used its cache. It turns out, as shown in the previous link, that most
browsers will do a new request for cached resources to see if it changed.
So one way to have a "normal" behavior is just to type `Enter` in the address
bar and then the browser will use its cache appropriately.
