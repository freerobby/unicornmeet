---
layout: post
type: post
title: Don&rsquo;t Make Me Wait
author: Chad Mazzola
---

Well-designed software doesn't allow the details of its technical implementation to dictate or degrade the user experience.

One of the most pervasive violations of this principle is the request/response model used by most web applications. Users are forced to submit each change to the server and wait for a response and subsequent page reload. [Alan Cooper](http://en.wikipedia.org/wiki/Alan_Cooper) calls this model "archaic."

Users of web apps that behave like this are forced to accommodate the needs of the software instead of the software catering to them. Users will always be better served by seeing the results of actions quickly and smoothly, with no interruption of focus due to page reloads.

The past few years have seen great strides in our ability to deliver these kinds of rich, seamless interactions on the web. The key is asynchronous communication between the client and the server. This allows the results of actions taken by users to be immediate and continuous, while server-side processing is done in the background without interrupting.

[Alex MacCaw](http://blog.alexmaccaw.com/), creator of [Spine](https://github.com/maccman/spine), [gave a talk](http://www.infoq.com/presentations/Asynchronous-UI) where he laid out three principles of asynchronous UIs:

<ul>
  <li>
    <em>Lie: update the UI asynchronously</em>
    <p>Show users the results of an action right away, even though the server has not yet returned a response.</p>
  </li>

  <li>
    <em>Cheat: pretend there&rsquo;s no server.</em>
    <p>Update the client-side and force the server to notify the client if there are failures.</p>
  </li>

  <li>
    <em>Steal: steal data from the client when they&rsquo;re not looking</em>
    <p>If a process must be done on the server-side, initiate the request as soon as possible rather than waiting for the user to send it.</p>
  </li>
</ul>

Delivering these kinds of rich, seamless interactions is more difficult than using the traditional request/response model. Development teams resist these techniques for that reason, but also because implementing rich interactions demand a more significant design effort.

When a state change is made in a request/response model, a message is usually shown that indicates success or failure, with the interface now in a different state than the last time the user saw it.

In an asynchronous interface, results of actions must be shown immediately. Transitions and animations that provide feedback to user actions, along with an intuitive and non-disruptive flow from one state to the next, are a primary design challenge.

In an inherently 2D medium, the third dimension that web designers have traditionally focused on is depth -- drop shadows, bevels, gradients and so on. When designing rich interactions, _time_ is the third dimension that matters. The interface must respond quickly and smoothly to user behavior in real-time. The priority is well-designed interaction, not the presentation of static pictures. Interaction over interface.

Implementing these kinds of interactions blurs the distinction between designer and developer. The view layer of web apps, which have traditionally been written in HTML, suddenly become dependent on JavaScript, stretching the ability of many designers to implement the interfaces they design. In addition, developers are forced to confront the challenge of not only performing actions on data, but representing these changes to users in the interface.

Quora [has built a framework](https://www.quora.com/David-Cole/Posts/Designers-Will-Code) that addresses some of these concerns by giving designers access to rich interactions without needing to write JS.

Rich interfaces that communicate asynchronously with the server are better for users, but they require more effort and investment from product teams. The influence of people who can understand both the design and implementation of them will grow.

