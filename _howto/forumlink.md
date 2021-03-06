---
layout: howto
title: Link to forums
linkas: false
feedback: "https://www.7cups.com/@RarelyCharlie"
---
7 Cups does not provide an easy and reliable way to link to threads or posts in the forum.

### First page links

To link to the first page of a thread, go there and copy the URL from your browser's addresss bar.

If it has a #-sign in it, remove the #-sign and everything after it.

If the URL does not end in `/1/` then you should add `1/` to the end of the URL. This ensures that the 
link always points to page 1 of the thread, even in the future when it has more than one page.

*Example:*

If the URL looks like this:

`https://www.7cups.com/forum/Subcommunity_123/Subforum_456/Thread_789012/`

Add the page number like this:

`https://www.7cups.com/forum/Subcommunity_123/Subforum_456/Thread_789012/1/`

Test the URL before you put it in a link.

### Specific page links

To link to a specific page of a thread, go there and copy the URL from your browser's addresss bar.

If it has a #-sign in it, remove the #-sign and everything after it.

The URL will end with a page number, like `/8/`, unless it's the last page (or the only page). In this case you
must add the page number, maybe `8/`, yourself as described above. If it's the first or only page, add `1/`.

### Last page links

To link to the last page of a thread, go there and copy the URL from your browser's addresss bar.

If it has a #-sign in it, remove the #-sign and everything after it.

If the URL ends with a page number, like `8/` then remove the page number. This ensures that the 
link always points to the last page of the thread, even in the future when it has more pages than now.

*Example:*

If the URL looks like this:
`https://www.7cups.com/forum/Subcommunity_123/Subforum_456/Thread_789012/8/`

Remove the page number like this:
`https://www.7cups.com/forum/Subcommunity_123/Subforum_456/Thread_789012/`

Test the URL before you put it in a link.

### Post links

You might be able to link to a particular post if your web browser supports it. First copy the URL
from your browser's address bar.

Remove any #-sign and everything after it. Add a page number if necessary, as described above.

Go to the post and right-click the top part of it to get a context menu. Choose Inspect from the menu.
In the list of elements, scroll up a few lines until you see something like `id="forum-post-1234567"`.
Copy the number part of the id that you see between the quotes. At the end of the URL, type a `#`-sign and paste the number.

*Example:*

A complete post link URL looks like:

`https://www.7cups.com/forum/Subcommunity_123/Subforum_456/Thread_789012/1/#1234567`

Test the URL before you put it in a link.

**Note:** When you click on a link to a particular post, 7 Cups hides the top part of the post underneath the
navigation bar at the top of the screen. This is a bug in 7 Cups.
