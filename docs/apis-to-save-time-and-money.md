# Backend as a Service: Use Snowpal APIs to save money (and time)

> saas.snowpal.com: Spend time building feature that are unique to your products as opposed to reinventing the wheel. Integrate APIs where it makes sense.

Say, you are implementing a Checklist feature (for one of your products, or for your clients if you are a Managed Services team) that looks like what we have on our Web App. 



It will require you to do a few things —

1. Create UI/UX designs to share with product team.
2.  Once product team approves (after a few iterations), you will communicate those requirements to your UI and API development teams.
3. Your UI team will want to work on creating the first version of the interface using stubbed out API Endpoints, so your API team will need to provide this ASAP. This takes time.
4. Before the stubbed out endpoints are made available, your UI and API teams will meet to discuss the specification when its ready, address gaps and concerns so your API team can tweak the specification to suit the specific needs.
5. When all teams are on the same page, they go about their ways to build their piece of the puzzle (UI teams will focus on building the interfaces iteratively while API teams will work on implementing the APIs and the associated endpoints).
5. After the real endpoints have been implemented, the UI teams will repoint their pages to the actual APIs (by disconnecting from stubbed out endpoints).
7. This will bring bugs to the surface which teams on both sides of the aisle will work on addressing.

Those are few of the main steps (and there’s more to that list). Let’s take a look at some of disadvantages with this old fashioned approach, if you will, but before we do that, let’s take a quick look at what some of the endpoints look like for the Checklist feature above.



We support Checklists at every level of the Snowpal content hierarchy so there are a lot more endpoints (one set for every resource to handle the nuances totaling over 70) but the list above should give an idea of the breadth of a feature that might look rather simple at first.

## Limitations of traditional approach

Now that we know how the UI looks like and what some of the endpoints are, let’s delve into the limitations of this traditional approach.

API team needs to be staffed and trained if you do not have one already.

If you already have a team, they will have to spend time, money and effort simply to reinvent the wheel and rebuild what’s already out there.

While your API is being developed, your UI team will need to work off of stubbed out endpoints and I’ve seen UI teams run the gamut on their reactions as some of them simply do not fancy this approach (or aren’t simply trained to do so).

Once the endpoints are ready, integration work begins and it typically results in plenty of surprises and modifications to endpoints in the 11th hour putting tremendous pressure on deliverable dates.

Your API teams will need to maintain, improve, scale and do much more to the APIs from that moment on to eternity.

Is there a way to eliminate a lot of these steps (and therefore, risks)? You bet!

## Introducing Snowpal APIs

When you use our APIs, you stand to benefit from many items, some of which are —

1. The APIs will be ready to go on day 1! All your team would have to do is understand our terminologies (we’ve made it simple) and map it to your requirements. We are more than happy to work with your team on it.

2. Your UI teams can start coding against real APIs and not have to worry about leveraging the stubbed out endpoints (that don’t always work well), or about the integration down the road (that sounds more like delaying the inevitable).

3. You do not need to hire & train a backend team. That’s a lot of time and money saved right there.

4. You will benefit from continuous feature and performance improvements made by us.

What we’ve taken above is a simple enough example to make the case that leveraging APIs will save you time, money and effort the first time, and every other time after that. So, before you reinvent the wheel next time, ask yourself if you should.
