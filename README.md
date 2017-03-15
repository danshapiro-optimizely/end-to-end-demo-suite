# Optimizely End-to-End Demo Suite (Python)

## Brief Description: 
 This site comprises a variety of "micro-sites" that SEs, AEs, and all customer facing Optinauts can use to show how Full Stack can work in tandem with Optimizely's web products to create a compelling demo. Each micro-site represents one of Optimizely's most popular verticals.

As of now, micro-sites included are:

* E-Commerce - Addison & Boss (deployed and live)
* Media - The Daily Optiverse (currently in production)
* Travel - Paradiso Travel (next in backlog)
* This demo suite attemps to augment Optimizely's current demo environments by adding Full Stack use cases. This will help solve the inherent issues that come with demo-ing Full Stack

## Customer Stories

### E-Commerce

This experiment involves a site-wide price test and associated sorting algorithm. The purpose of this experiment is to test whether appealing more to price sensitive shoppers will increase revenue. Someone bucketed into the 'price_sensitive' variation will see a 15% price reduction on all products over $8,000 as well as an altered sorting algorithm on the product listing page that displays discounted bikes first. This is testing whether the price discount will make people want to buy more extensive bikes. When the customer moves to the product details page they will see the same reduced price as well as an option for financing.

## Using the Demo Suite

### For AEs

#### Navigating to the site and choosing a user ID

Go to the Demo Suite Homepage and click on the micro-site that matches the vertical for your given customer. Optimizely will assign a random user ID that will be persisted across the experiment. If you'd like to override the random user ID, clear your cookies after entering the micro-site, and add a query parameter at the end of the url. For instance, if you want to assign someone's name as the ID on the shop micro-site it would look like this ('demo-suite.herokuapp.com?id=dan'). The value 'dan' will act as the user ID. At any point you can clear your cookies, return to the homepage and enter a new user ID. This feature can be used to show Optimizely's bucketing in action.

#### Demonstrating Full Stack's capabilities

There are helpful buttons, labeled 'Full Stack Experiment Information' at the top of each page within each micro-site. When clicked, this button will display a modal that explains the name of the experiment running on the page, the underlying hypothesis, the variation you've been bucketed into, and an explanation of what's happening underneath the hood. These modals are scoped to each individual page and will change based on what's happening. This should provide enough information for non-technical users.

### For SEs/Technical Users

#### Showing the code

If you are an SE, Engineer, PM, or any other technical user that is demo-ing to a technical audience, you will likely want to show the underlying code during the demo. You should clone the End-to-End Demo Suite Github Repo and walk the user through the code. The demo suite is written in Python and the structure of the app may be confusing if you are not familiar with Python/Django. Generally, there are only two main files that you need to show:

Any file named views.py. These files contain the routes for each micro-site and are where the Optimizely experiments live. Each micro-site has its own views.py file and they can be found within each micro-site's labeled directory
The optimizely_config_manager.py file contains the manager responsible for pulling down the Optimizely datafile. This can be used to detail how a Full Stack environment is set up and how you can automate the pulling down of the Optimizely datafile.

## Technology Used

This suite is built exclusively in Python. Below is a working list of the technologies being used to run/host the demo suite:

* Django
* HTML5
* CSS3
* jQuery  
* PostgreSQL
* Heroku

## Notes on Code Style

We've tried to confine as much of the Optimizely experiments to each micro-site's views file as possible. In a production environment, much of this will be abstracted away into helper methods and models, but the thinking here is that keeping as much as possible in one place will reduce the need to click through multiple directories, and thus, improve demo flow.
