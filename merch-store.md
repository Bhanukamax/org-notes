





Hi team,

Right now there is a bit of delay in the following steps in the merch store:
* Clicking and opening a product
* Redirecting back to store (product list) after adding a product to the basket.

Reasons for the delay:
* Fetching data every time we redirect
* Router delay

Regarding caching ideas:
 * Use service worker
     * I tried to implement the PWA features, but with `next-pwa` we cannot have much granular level control. And building caching using Workbox need a bit of learning which may take longer.
 * We can also use zustand (a simple redux like library, we already have in the app) for caching in the local storage.

Routing ideas:
* Conditionally rendering the product view or product list view (maybe using query params) in the same base route.
    * with this we can reuse some of the data in the listing page so we can start to already show the product while fetching things like the full size image in the background.
    * and also with this no need to redirect at all.
* Another option is that next.js does support something called `Shallow routing` which also only works with query params, but I haven't played around it with much. I can try doing this too.

I'd like to try out the Routing changes that I mentioned above as those will be fairly quicker to implement.

with these routing changes there will be no change for the end user flow (other than possible speed improvement)


@Felix
I remeber you brought up slack markdown support once.

I found this option which makes slack not convert your markup to rich text until you post it, so it kind of easier to work with markdown, but still it's not the best experience.

What you can basically do is, write it in markdown in your editor and slack it to yourself first to see how slack took it :)


Hi Team:
I'm signing off for today.
So today:
* I fixed the analytic issues there were on both Pickup and Servedup light projects.

Please give me any feedback you have regarding the Merch store changes I mentioned above, when you have time.

I am planning to look more into implementing service worker caching with workbox in my spare time by trying to add it to my personal blog.
probably a bit tomorrow or during the weekend as I get time. So if I learned anything out of it, I can apply that to merch store hopefully :)
