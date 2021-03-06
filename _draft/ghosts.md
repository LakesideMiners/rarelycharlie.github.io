---
title: Ghosts
layout: default
feedback: https://www.7cups.com/@RarelyCharlie
---
<style>
#content {counter-reset: prop;}
strong {display: inline-block; margin-right: 1ex;}
strong::after {counter-increment: prop; content: " " counter(prop) " ";}
img {display: block; margin: 0 auto; width: 640px;}
img.auto {width: auto;}
.caption {text-align: center; font-size: 80%;}
</style>
Here are some practical proposals to mitigate the problem of ghosting in chats.

Ghosting means when someone stops communication without warning. I'll call chats where this happens *abandoned*.

This is a complex problem, unfortunately, and my proposal is complex too. I don't believe it is possible to prevent abandoned chats entirely, but I do believe they can be managed better.

I think many of the proposals in this paper can be implemented independently one at a time. I haven't thought much about the best order of implementation.

### Analysis

It's OK for a member to request a chat but say nothing. The member might be too nervous, or too upset, or they don't really have anything to say and they just wanted reassurance that 7 Cups really does connect them with a listener. They might try again another time, and this is OK too.

It's also OK if a member chats for a while and then abandons the chat. We can't penalize members when we don't know anything about their circumstances.

Because it's not possible to prevent members from abandoning chats, I suggest taking steps to limit the impact on listeners.

It is not OK for a listener to take a chat and then say nothing.

I suggest taking steps to limit the impact on members, to encourage reporting of listeners, and to make reporting more effective.

To handle these situations appropriately, the system needs to be able to determine reliably when a chat is abandoned. This requires greater clarity in the system about when a chat is live and when it's not, and because this is closely related to members' and listeners' status (Online/Busy/Offline) it requires greater clarity about that too.

Additionally, if there are preventable situations that tend to result in members or listeners abandoning chats, then we should do whatever we can to reduce the occurrence of those situations. However, this requires a wider discussion, probably resulting in changes to listener training and support, and therefore is beyond the scope of this paper.


### Approach

In summary, I suggest four approaches and elaborate on three of them in this paper.

*Change the chat system so it can reliably determine when a chat is abandoned.* This involves a significant change to the way the End Live Chat button works.

It's a big deal, because it will involve asking members and listeners to change the way they end chats. There will have to be a pre-announcement, a period of discussion and clarification, a change in the software platform, follow-up information, and perhaps a transition period before the new way of ending chats becomes mandatory.

*Enhance the user interface so that it provides greater clarity.* There are three parts to this: chat mode, Online/Busy/Offline status and response time. All the proposals are easy, involving changes to the software platform that should be self-explanatory to members and listeners.

1-to-1 chats have always operated in two modes. In a *live chat* both chatters should respond quickly to keep the conversation going. In what is currently called an *offline chat* response time is less critical.

The term "offline chat" is easily confused with offline status, but they are not the same. For clarity, I propose using the term *messages mode* instead. This is also better aligned with our well established use of the abbreviation PM to mean personal message.

Online/Busy/Offline status currently lacks clarity. Some new members, and even some new listeners, seem to be unaware of what it means. Members and listeners who suffer from the commonest (red/green) colour vision deficiency may be unable to interpret the status indicators at all.

There's a lack of clear information, both for listeners and members, about expected response times.

*Limit the impact of abandoned chats on members and listeners.* Accepting that abandoned chats can't be eliminated completely, some things can be done to limit their impact in particular cases.

*Reduce preventable situations that tend to result in abandoned chats.* Not discussed further at this time.


### Proposal to identify abandoned chats

*Problem:* It is not OK for a listener to stop responding unexpectedly in the middle of a live chat.

Note that the system currently has no way of "expecting" the listener to stop responding, therefore it has no way to determine whether the listener stopped "unexpectedly" or not.

To help set expectations and allow the system to identify abandoned chats, the proposed solution is:

**Proposal** Change way the the End Live Chat button works. It will now inform the system and both chatters that the live chat is *expected* to end. The proposed ending period is 8 minutes.

The *other* chatter (the one who *didn't* press the End Live Chat button) must send at least one further message within the 8 minutes. Otherwise the system will mark the chat abandoned by that other chatter.

When a conversation switches between the two modes, live and messages, the messages are never cleared because either chatter might want to continue sending messages.

The following mockup shows a listener ending a live chat normally:

![Screenshot](/assets/ghosts/ss01.png)
Listener ending live chat normally
{:.caption}

In this example, member and listener are both online. The listener presses the End Live Chat button (1:04 PM), telling the system the chat is expected to end. The system immediately informs the chatters (1:04 PM). The chatters can exchange messages briefly. 

8 minutes after the End Live Chat button was pressed, the live chat ends and the conversation switches to messages mode (1:12 PM). The conversation header now says Messages <i class="fa fa-pencil"></i> and the message timer (bottom right) is disabled.

The following mockup shows a listener ending a chat that the member abandoned:

![Screenshot](/assets/ghosts/ss02.png)
Listener ending abandoned chat
{:.caption}

In this example, the member has abandoned the chat. The listener presses the End Live Chat button (1:20 PM) but there is no response from the member. When the chat times out and switches to messages mode (1:28 PM), the system knows that the chat was abandoned because the member didn't respond.

The following mockup shows a chat that seems to be about to end, but is then resumed:

![Screenshot](/assets/ghosts/ss03.png)
Live chat resumed
{:.caption}

In this example the person who pressed the End Live Chat button sends a message more than 5 minutes into the ending period. The ending period is cancelled and the chat is resumed. The conversation header now says Live <i class="fa fa-comments-o"></i> and the message timer is running.


### Supporting proposals to provide clarity and set expectations

*Problem:* It's not easy for chatters to keep track of time, and they might not always realize that they have taken a long time to respond in a live chat. To help set expectations, the proposed solution is:

**Proposal** A timer displays the time since the last message in a live chat, but it's disabled in messages mode. There is information about what it's for.

![Screenshot](/assets/ghosts/ss04.png)
Message timer information
{:.caption}

*Problem:* It's not clear to chatters whether a chat is live or in messages mode. Members sometimes send "Are you there?" messages to listeners who are offline or logged out. To help set expectations, the proposed solution is:

**Proposal** The chat mode (live or offline) is shown at the top of the chat, together with further explanation.

![Screenshot](/assets/ghosts/ss05.png)
Top of chat showing information about each mode
{:.caption}

*Problem:* It's not clear to everyone what the listener and member status indicators mean, and they're completely meaningless to people who have the most common (red-green) form of colour vision deficiency. To help set expectations, the proposed solution is:

**Proposal** Change the status indicators so they use either text (if possible), or shape, in addition to colour. Improve the colour contrast for better clarity without colour vision. Add information explaining what the status means.

![Screenshot](/assets/ghosts/ss06.png)
Status indicator in Browse Listeners, using colour and text
{:.caption}

![Screenshot](/assets/ghosts/ss07.png)
Status indicator in forum, using colour and text
{:.caption}

![Screenshot](/assets/ghosts/ss08.png){:.auto}
Status indicators in chat list, using colour, shape and text
{:.caption}

*Problem:* The system doesn't reliably know whether a chat is live or in messages mode. As a result, chatters don't reliably know what's expected of them. To help set expectations, the proposed solution is:

**Proposal** A chat is live either if the chat is new (no messages at all) and both chatters' status is Online, or if both chatters have sent messages in the last 8 minutes and both chatters' status is Online or Busy. The chat's current mode (Live or Messages) is clearly displayed to the chatters.

As soon as conversation in messages mode satisfies this condition, it immediately goes live and the chatters are notified.

![Screenshot](/assets/ghosts/ss09.png)
Chat just went live
{:.caption}

However if a chatter goes offline, the chat mode doesn't immediately change. This is because people sometimes get disconnected for short periods and soon return. The 8-minute timeout described above still applies.

*Problem:* Listeners whose star ratings are poor, or become poor, can still be verified. This gives a misleading impression to members. Star ratings are important, both to help set members' expectations and because a further proposal (below) makes use of star ratings to help limit the impact of ghosting.

The proposed solution is:

**Proposal** Make a 4-star or better rating a requirement for becoming and remaining verified. If a listener's rating drops below 4-stars, they become unverified and must reapply when they meet the requirement again.

The following mockup shows the proposed new requirements. Note that there's an error in the graphic that I have not corrected (Categories are not a requirement):

![Screenshot](/assets/ghosts/ss10.png)
Requirements to become and remain verified
{:.caption}

*Problem:* When a member starts a chat with a listener who is busy or offline, the chat is in messages mode, but the member doesn't always know what this means. Members sometimes feel abandoned when there was in fact no live chat. To help set members' expectations, the proposed solution is:

**Proposal** After a member sends the first message in messages mode, the system reminds the member that the listener might not be able to respond quickly. (In fact the listener might be on a long break or have left 7 Cups altogether, but this is difficult to deal with.)

![Screenshot](/assets/ghosts/ss12.png)
Reminder in new messages mode conversation
{:.caption}


### Supporting proposals to limit impact

*Problem:* A member can end a chat or block it immediately, without ever saying anything, then go on to make further chat requests and end or block them too. Multiple listeners experience being ghosted.

A neat solution is impossible. Blocking a chat is genuinely necessary if the listener's first messages are inappropriate, but the system doesn't understand what bad things the listener might have said.

To approach a solution, let's assume that only weak (less than 4-star) listeners are likely to make inappropriate remarks, and only new (Embraced-level) members are likely to end or block chats inappropriately.

To limit the impact on members when listeners say inappropriate things, and to encourage effective reporting, the proposed solution is:

**Proposal** When a member ends or blocks a chat, or a live chat times out, without the member saying anything in the chat, but the listener did say something, then if the member agrees, the chat is automatically reported, and the report automatically quotes the listener's messages.

Note that the member said nothing, so there is nothing confidential in the listener's messages.

![Screenshot](/assets/ghosts/ss13.png)
Confirmation that a chat will be reported automatically
{:.caption}

*Problem:* When a member abandons a chat, the listener is left waiting indefinitely. To provide clarity and limit the impact, the proposed solution is:

**Proposal** A live chat times out if either one of the chatters hasn't sent a message or typed anything in the last 8 minutes. The system warns that chatter after 5 minutes. After a further 3 minutes the chat switches to messages mode and the system notifies both chatters. The messages are not cleared.

If the listener sent the last message, it's the member who must have abandoned the chat. This is OK.

**Proposal** If the member sent the last message, it's the listener who must have abandoned the chat. To encourage effective reporting, the system asks the member whether they want to report the listener.

*Problem:* A member can make multiple chat requests, abandoning them all and leaving many listeners waiting. To limit the impact on listeners, the proposed solution is:

**Proposal** When a chat is currently live, the member cannot make a chat request (general or personal). Attempting to make a chat request just returns the member to the current live chat (or one of them), and notifies the member what happened.

Note that this does not prevent a member from chatting to many listeners at the same time, if they are listeners the member has chatted to previously. It would be possible to limit the number of simultaneous live chats, but I'm not proposing that here.

To limit the impact on listeners when a member ends or blocks multiple chats, the proposed solution is:

**Proposal** A new (Embraced-level) member who ends or blocks a chat with a 4-star or better listener after sending fewer than 10 messages in the chat has a 20-minute waiting period before they can make another chat request.

This reflects the assumption if the member is experienced or the listener is weak, the block is more likely to be genuine.

Note that this does not prevent the member from chatting with any listeners they've chatted to previously.

*Problem:* Giving a listener a bad rating doesn't always affect the listener's stars, so that some listeners who have 4 or 5 stars behave inappropriately, and members abandon chats with them.

Inaccurate star ratings would unfairly affect new (Embraced-level) members under the proposal above, because they'd be vulnerable to weak listeners who have many stars but nevertheless say inappropriate things.

To limit the impact on new members, the proposed solution is:

**Proposal** Weight the calculation of listeners' star ratings so that recent bad ratings have a visible effect. Notify listeners of changes to their star rating.

For example, an appropriate algorithm would be that the new star rating is the average of 6 of the old rating plus 1 of the new rating, rounded up to the nearest ½-star.

Note that this will probably mean that even the very best listeners' 5-star ratings will be less stable.

![Screenshot](/assets/ghosts/ss11.png)
Notification of star rating changes
{:.caption}

*Problem:* It is not OK for a listener to take a chat and then say nothing. To limit the impact on members and to encourage effective reporting, the proposed solution is:

**Proposal** When a new live chat times out (switching to messages mode after 8 minutes), and there is at least one message from the member but none from the listener, the system asks the member whether they want to report the listener.


### Notes

 - Chatrooms should not be affected by any of this.

 - Listener-listener chats are proposed to be always in messages mode.

 - Listeners sometimes abandon conversations in messages mode. No change in relation to this is being proposed. The member should report the listener in the normal way.

 - Implications for listener training and support are a story for another day.

