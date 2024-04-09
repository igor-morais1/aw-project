# micro-frontend-division

* Status: accepted
* Deciders: Igor
* Date: 2024-03-08

## Context and Problem Statement

What is the best way to divide the given mobile app (Meat) in terms of micro-frontends, in such a way that makes sense?

## Decision Drivers

* Simplicity
* Single responsibility
* Reusability
* Independent deployment
* Autonomous teams
* Vertical services
* Flexibility

## Considered Options

* Login + Search + Feedback + Saved + News
* Login + Profile + Search + Feedback + Saved + News + Stats + Scanner

## Decision Outcome

Chosen option: "Login + Search + Feedback + Saved + News", because overall it makes more sense to have a simplified option.

### Positive Consequences

* More stable development of the app
* Less waste of resources

### Negative Consequences

* Possible delayed introduction of new functionalities

## Pros and Cons of the Options

### Login + Search + Feedback + Saved + News

Login = Login, authentication, profile management, settings.
Search = Supermarket locations, Categories of products and products list.
Feedback = Feedback on each product and rating.
Saved =  Saved products from each supermarket.
News = News section including Stats.

* Good, because Login: Includes everything related to the user's login; Makes it really easy to reuse and segregates it's responsibilities within the app; We can have an autonomous team taking care of it, without constant need of communication with the profile team (more autonomous system).
* Good, because Search: Autonomy was a big reason, with a similar explanation as the login team. Having the Products and Scanner integrate the Search facilitates the whole team's work. We can have a more specialized search system when they also take care of the products, allowing the team to develop a more optimized solution.
* Good, because News: Stats wasn't as big of a category or complex, to justify a specific team. Topics are closely related.
* Bad, because Future introduction of new fuctionalities might overload some teams that deal with big sections of the app; Creating teams with big tasks might delay some of these new fuctionalities since they would not have time to develop them.

### Login + Profile + Search + Feedback + Saved + News + Stats + Scanner

Login and Profile separated.
Scanner specific micro-frontend.

Login = Login + Authentication 
Profile = Profile + Settings
Search = Supermarket locations and Categories of products
Products = Products list
Feedback = Feedback on each product and rating
Saved = Saved products from each supermarket
News = News section.
Stats = Statistics for each year (positive and negative)

* Good, because Login + Profile: It would separate the two areas in parts that make sense, since the profile and settings aren't as close to the login as the authentication is.
* Good, because Scanner: Allows for future introduction of additional functionalities such as a bar code reader, making it a more complex/particular part of the app, thus requiring a dedicated team; Is different enough of the rest of the app to be considered a section on it's own - it has independent functions
* Good, because Stats: Allows for future introduction of more functionalities regarding statistics.
* Bad, because Login + Profile: There is no need for two different teams to take care of these areas.
* Bad, because Scanner is a really simple micro-frontend, can be integrated within the search team; Some of it's functions are dependent on the Search team, so autonomy is an issue.
* Bad, because Stats: It is a super simple micro-frontend, there is no need for a dedicated team.
* Bad, because More complex solution.
