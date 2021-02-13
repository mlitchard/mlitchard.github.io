
## Who we are
Three years ago, I met fellow Haskeller Brian Hurt while working with Obsidian Systems on a Reflex project. Not long after, he started telling me his ideas about how to fix social media. These ideas intrigued me, one thing led to another, and we began building ChatWisely. We thought other Haskellers might like to hear about what we’re doing and how we use Haskell to do it.

## What we're doing
ChatWisely is a member-supported mini-blogging social network currently in open beta. We want to elevate discourse and show bullies the door by providing a platform to debate safely.We want a place where people connect and the conversation continues. Here’s how.

How we're doing it
<p align=center>Safety First</p>
We have several mechanisms to filter out people looking for a fight or to harm others. First and foremost will be the monthly subscription fee of one dollar. We think that will discourage a large portion of toxic people. Another is a sharable mute list that we believe will help mitigate most of the rest. And finally, in the event of a serious Terms of Service violation, we ban payment methods rather than just accounts. 

Mini-Blogging
ChatWisely supports short form blogging that easily connects to optional longer posts. These can easily be connected to other people’s posts, to build real connected communities. So when another member’s post inspires you to write a longer one about your experience with the ghcjs ffi (for example), you can link your post to theirs.

Ownership of Your Timeline
ChatWisely lets you organize your timeline and choose to what extent you follow other people’s posts. The typical mainstream social network requires that when you follow someone you must follow everything they post, or nothing. Sure, there are filtered word lists in some cases. But none of it seems to work quite right. With ChatWisely, we have groups we call caboodles that you can use to decide where other people’s posts fit, and how to share your own. So say you like your uncle’s cookie recipes but not his political posts. Follow one but not the other.

Geolocated Messaging
One day this pandemic will be over and we’ll be there to meet that day. So when your movie caboodle wants to organize local screenings of the latest blockbuster from the House of Mouse you can make posts visible to people in your proximity. Perhaps you want to target local Haskellers to organize a meetup, or leave them a message that pops up when they’ve found the meeting place. Or for something completely different, running a scavenger hunt with geolocated clues sounds like a hoot.

How It’s Built
Brian and I rely heavily on the Haskell ecosystem to build ChatWisely. Haskell’s type system reduces errors and cognitive load. GHC is our pair programming partner that tightens the delivery cycle and lets us learn how to build ChatWisely while we’re building it. Refactoring is a breeze, and unit testing is constrained to the I/O edges of the system, which means we spend less time on that and more time building the product. Here’s the principal tools we rely on to get the job done.

Ghcjs - The fact is we all hate javascript. The problem is, we can’t build web apps without it. Ghcjs lets us deal with the realities of building a product that uses a web browser for a client. The FFI lets us wrap our hand-written javascript in Haskell which helps to keep that part of the codebase pretty small.. We especially love what is built on top of that, Reflex-Dom.
  
Reflex-Dom  - Reflex helps us build a system that needs to adapt to changes in data, requirements and platform. We’re learning how to build ChatWisely as we build it, and reflex keeps up with our changing ideas on how to do that. Our first app store product will be a PWA, delivered with reflex.

Servant - Servant delivers the API, and requires us to separate definition from implementation. This helps us keep the backend from turning into a big ball of mud. We can auto-generate clients, which we currently use in unit testing. They even have a way to generate a reflex client, and we’ll be adding that in the near future.

Yesod - We use Yesod for marketing tasks, which largely require static pages. Currently it handles our landing page and unsubscribe mechanism for our emails. The Yesod Widget is a monoid, and therefore composable, which makes structuring html simple. 

Postgres - We love postgres for its stability. It has also helped us deal with some duplicate post problems we had, using its recursive query feature. When it came time to implement search, most of that work was done with postgres, which resulted in quick delivery.

Three Reasons Why People Should Use ChatWisely.
We are member supported - We won’t have ads, which means we have no need to manipulate your timeline to serve them. Your timeline should be about conversations that interest you.

We solve the tweet thread problem - Tweet threads are hard to follow. Our mini-blog looks like twitter in the sense that you get a timeline of short posts. However if a post is the beginning of something more developed, that message can open up to access it.

Keep the RealWorld conversation going - We have delayed the development of these features for obvious reasons. But one day we’ll be together again. And then ChatWisely will have useful geo-location tools for conference attendees and speakers to continue the conversation. 

What makes a weekend conference fun are the conversations in between the formal talks. We all get caught up in compelling conversations with each other. We’ll have a seamless way to keep that going, without having to know or remember anyone’s e-mail address or phone number.

Conference speakers will often want to build on the momentum gathered after a successful talk. Twitter hashtags are the terrible but often only way to do this. We’ll have a way to use proximity and common interests to help build that momentum and keep everyone engaged

We built ChatWisely as a response to the unpleasantness all too common on mainstream social networks. Depending on our membership for support creates the place we want to meet. Ad revenue and data-mining motivates engagement, not conversations and connection. And what mainstream social networks call engagement looks to us like derailed conversations, confusing timelines we only have a shallow control over, and unsafe situations.

We love the daily experience of building ChatWisely, the Haskell ecosystem brings joy to the experience of running our startup. You can support us on patreon and should come by and test the beta. We look forward to hearing from you about any ideas or questions you may have.


