# How to start with autotests

This article is not about the technical details on how exactly to write autotest, but rather about the approach one could take to ensure autotests initiative is not rejected.

Once you’ve [persuaded your manager](tests-persuasion.md) to support automated testing, you need to plan it right — the acceptance of the initiative doesn’t guarantee unlimited probation time.

Remember, step into the manager’s shoes: once having yielded to someone’s plan, they still nurture the doubts and hesitations. Provided there are no noticeable (and by noticeable I mean measurable) results, those hesitations and doubts will cherish.

Let’s see what we can do with numbers.

Quoting my previous article on the topic:

> It's a widely accepted consensus that automatic tests (and TDD) benefit the software development process in the following ways:
>
> - saves time (reduces time to market) [[link](https://www.techwell.com/sites/default/files/articles/XDD6027filelistfilename1_0.pdf)]
> - improves quality and lowers total cost of ownership [[link](https://martinfowler.com/articles/is-quality-worth-cost.html)]
> - improves team morale (mundane, repetitive tasks are among the sources of developers’ unhappiness) [[link](https://github.com/sharovatov/teamlead/blob/master/articles/happiness.md)]
> - reduces onboarding costs (developers have less fear of changing and breaking things)

There’s a consensus in the software development area that [**measuring quality** is a bad idea](https://www.satisfice.com/blog/archives/487091), so I wouldn’t recommend going that route.

It’s also impossible to measure **team morale** with numbers, so this route is useless too.

We can show only two measurable things: **onboarding cost** (time) and **time to market**.

However, **onboarding costs** will reduce noticeably only after some time while we want to show immediate results.

So we are left with showing how **time to market** is reduced.

TTM comprises the time taken to pass all the steps required to develop and deliver certain functionality to the client.

The manual QA stage usually takes significant time: a feature awaits for the QA team to pick it up, and then the testing itself is done.

Also, the manual QA stage implies massive delays in a case when the feature is returned to development due to defects.

The reason for the delay is that when the feature is passed to QA, the developer usually picks a new feature to work on, and when the tested feature is passed back to development, it has to wait again.

If the developer picks the returned feature straight away, context switch costs apply.

I’ve mentioned studies on context switching costs in my [code review limits to applicability](https://hackernoon.com/code-review-its-bad-expensive-and-ineffective-in-most-cases) article:

> There are multiple publications on how multitasking and switching contexts are ineffective:
>
> - [The myth of multitasking, Nass, 2013](https://www.npr.org/2013/05/10/182861382/the-myth-of-multitasking)
> - [Multitasking: Switching costs (american psychological association)](https://www.apa.org/research/action/multitask)
> - [Executive Control of Cognitive Processes in Task Switching — Joshua S. Rubinstein, David E. Meyer, Jeffrey E. Evans](https://www.apa.org/pubs/journals/releases/xhp274763.pdf)
> - [Reconfiguration of task-set: is it easier to switch to the weaker task?](https://pubmed.ncbi.nlm.nih.gov/11004879/)
> - [Executive Control of Cognitive Processes in Task Switching](https://www.apa.org/pubs/journals/releases/xhp274763.pdf)
>
> There’s good scientific evidence that it’s more effective to work on one single task at a time with as few context switches as possible.

This proves that to reduce time to market (and show immediate results in this initiative),  manual QA phase should be reduced as:
- automatic tests run as soon as the developer runs them (0 waiting time)
- automatic tests run quickly (much lower testing time) and therefore provide almost instant feedback, meaning that there will be no context switching cost.

## Where to start

As we want to show our manager some immediate benefits, obvious idea would be to start with automating something that would show immediate results.

I’d advise automating tasks that have significant ‘manual testing’ time.

Every task tracker can show you the time a task spends in the ‘testing’ phase, and if you use a test management system, you can get even more information.

Here’s what I have in my [Qase](https://qase.io) TMS:

![testing time screenshot](https://github.com/sharovatov/teamlead/blob/master/articles/testing-time.PNG?raw=true)

As you can see, the obvious choice here would be to start automating ‘authorisation’ first as it takes 9 minutes to be tested manually every release.

These 9 minutes yield **8 hours a year** spent on manual testing of this particular feature if we have one release per week.

As soon as we automate this check, we can show our manager that TTM is reduced by 9 minutes for each task. This will inevitably gain us more trust.

The more trust you have, the more you can do what **you know is right**, potentially something which cannot be ‘measured’ or is not quantifiable.

[Deming](https://en.wikipedia.org/wiki/W._Edwards_Deming) calls ‘managing only what’s quantifiable’ one of the [7 deadly diseases of management](https://deming.org/explore/seven-deadly-diseases/):

> 5. Management by use only of visible figures, with little or no consideration of figures that are unknown or unknowable.

But I’ve rarely seen managers knowing of this, hence this whole approach of showing results and gaining trust to do something that’s truly right.

So, to summarise:
- you persuaded your manager to support autotests
- you constantly show them immediate results
- you gain trust to be able (and have resources) to develop proper testing strategy
- you start doing what’s right

To proceed with the proper testing strategy, first check Fowler’s [document](https://martinfowler.com/articles/practical-test-pyramid.html).


