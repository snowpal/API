# Access Control List API: Share your content with other users by granting them granular access that is customizable

Access Control needs vary for each app. Sure, there may be similarities between some of the requirements but what tends to make things sometimes more complex than they really need to be are the nuances. The devil is in the detail, as they say. 

Let’s take a look at a practical implementation of an app in production and delve into its access control model.



In the screenshot above, a resource (1040, as we near the tax season!) is shared with 2 users, Raj and Jerry. Raj has Write access while Jerry has Admin access. There are 3 possible access levels:

Read: user can view but make no modifications

Write: user can make changes but cannot grant access to other users

Admin: user has all privileges

If you asked your UI Developer to implement a React Page to support the requirements above, it would be pretty straightforward to them from a UI implementation standpoint. All they are going to ask you for are the API Endpoints that they need to call, and your API team would provide a specification with the respective endpoints as below.



If the API is already implemented and ready to go, it will make this feature as seamless as it can possibly be, and your stakeholders are bound to be pleased.

Now, let’s assume this API, and its related endpoints, are not ready. They need to be designed, implemented, tested and deployed before the UI developer can start integrating. Suddenly, things seem a lot more complicated, don’t they?

There’s 2 options available in this scenario —

Option 1: Implement the very basic that’s needed

There’s 3 levels of access (aka, privileges), no notion of roles and there is no need to support teams (as a group of users). Have your API team get started with development work and only work to satisfy your current needs.

It will still take them time but being myopic is going to be cost-effective, even if only in the short run.

The risks — well, when your needs evolve (as they surely will), this design is not going to cut it and your API team might find themselves in a pickle as they will have to go back to the drawing board, rethink, reimplement and also worry about Backward Compatibility.

Option 2: Think ahead and make the API a bit more generic 

Do it the right way (even if not the perfect way, the good way). Ask questions to your product team along the lines of:

Do we need to support other privileges in future?

If so, will be they predefined or should we also support custom privileges (ones that are not supported out of the box)?

Is there a need to support roles (a bag of privileges, that is)?

What about teams (aka, organizations) that group users?

This will take a few iterations before you can finalize requirements, and once finalized, your API team can work on implementing a more generic and extensible API.

The risk — well, it is going to take a lot longer, there’s going to plenty more testing needed given the broader set of features, your UI team may not get a drop for a while and that would mean they would have to live with stubbed out endpoints a lot longer and run the risk of bugs being found much later down the road when you get to Integration Testing.

Both these options have their pros and cons but what if there were a 3rd option that included the best of both worlds?

Well, don’t you worry because there is one! 

Introducing Snowpal’s Access Control API

All our APIs have support for basic access control but to make things sweeter for our clients, we have also introduced an exclusive Access Control API.

It has everything you should need from an Access Control standpoint, and it is ready to be consumed — as of this moment! Take a look at that, and let us know if you have any questions.

Snowpal Products

Backends as Services on ⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠AWS Marketplace⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠

Mobile Apps on ⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠App Store⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠ and ⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠Play Store⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠

⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠Web App⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠

⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠Education Platform⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠ for Learners and Course Creators

