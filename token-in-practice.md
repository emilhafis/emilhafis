# Token in Practice





> In a few following videos I will tell you more about gateways, but before we do this I would like to cover the very interesting concept of a token in BPMN. Token is not something physical.
>
> It is not something visible but this is a theoretical concept that helps you understand much better how does the process flow.
>
> So let's take a look at a simple example. You already know this process from previous videos.
>
> How would a token behave in such a process? When the start event happened, when it was triggered, so when we felt that "coffee \[is] needed" token was born. Then, token flows from the Start event following a Sequence flow.
>
> So it moves right to the first task "Check available options".
>
> It does not necessarily mean that we need to start checking available options right away but that the task is available.
>
> It also means that we cannot "select coffee" before we perform a task "check available options".
>
> So this is very important.
>
> Token showed us which tasks can be done and which are not available yet.
>
> So after it was made available and we finished this task, token moves and we can "select coffee". Than, after
>
> it's done, it moves to the Sub-process "Payment". And here let's see what would happen level below
>
> When the Sub-process was made
>
> active
>
> inside this Sub-process
>
> additional token was born also starting the Start event. By the way
>
> This is why normally in the Sub-processes we have Start events without any triggers. \[It's] because they are called
>
> from a top level process.
>
> So here the token moves to the first element and then if we are having Exclusive Gateway like in this
>
> case it can take either "yes" or "no" path.
>
> Let's assume that we can pay with a card, so our token moves here and after we finish task "pay with
>
> a card" it is right at the End event \["Payment performed"].
>
> It means that this instance of a (sub)process is done.
>
> It means that since the payment process is finished the token can move the next element:
>
> "Take coffee". After we take the coffee, the token is right at the End event and our instance can finish with a happy
>
> end i.e.
>
> The coffee is ready to drink.
>
> So this is how tokens look like in practice.
>
> Autoscroll
>
> ###
>
> ### Course content
>
> ### Overview
>
> ### Q\&AQuestions and answers
>
> ### Notes
>
> ### Announcements
>
> ### Reviews
>
> ### Learning tools
>
> \
>
