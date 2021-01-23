# CSharp_LP
Code summary of C# Live Project

 * [AJAX](#ajax)
 * [Models Without Photos](#models-without-photos)
 * [Donation Index Page](#donation-index-page)
 * [Rental Create Page](#rental-create-page)
 * [Skills Learned](#skills-learned)

## Intro
During a two week sprint, I worked collectively with my peers to contribute towards a content management system for a theatre company. The majority of my tasks focused on tweaking previous code to include requested features and create a more user-friendly experience. This project gave me a better understanding ASP.NET MVC structure and gave me a hands-on experience of learning already-existing code in order to improve on it.

## AJAX
Two of my stories required using jQuery Unobtrusive AJAX to update modals asynchronously. The first story asked for the functionality of being able to save a photo into the database without refreshing the entire page. After saving to the database, the story then wanted to be able to select that newly added photo as the default promotional photo within a modal containing all other photos associated with the same production. For the second story, I needed to update the body content of a modal depending on who's details we we're trying to bring up. This modal was specific to individuals who had recently donated to the theatre and would display to the admin how much they donated, when they donated, email, etc. After completing both of these stories, I feel a lot more confident utilizing partial views and updating sections of a page asynchronously.

## Models Without Photos
Within the AdminSettings.json file, our team wanted to keep track of every model that no longer had an associated photo. (Some examples of those models include Productions, Cast Members, Sponsors...) My story was to adjust the Photo Delete method so that it updated the json file with the IDs of any models that relied on the deleted photo. Those models (now flagged in AdminSettings.json) were then displayed on the admin's homepage as missing a photo so the admin could update or handle those models as needed.

## Donation Index Page
The Donation Index Page was accessible only by the admin and displayed all recent donations within a table. Though this story was rather simple, it was one of my favorite avenues of programming - styling and CSS. The tough part with this story was avoiding overriding any Bootstrap classes or classes created by other students. My work around was creating a lengthy id; "#donation-index-table" and targetting the needed html elements ie, #donation-index-table tr, th, td and so on.

## Rental Create Page
This was my last and maybe most challenging story. The theatre company wanted to be able to keep track of items/studios that were being rented out. When I started this story, we had a base Rental class and an Equipment Rental and a Room Rental which both inherited the base properties from Rental. All three were saved into the same table in the database, and within the table they were flagged as Rental, Equipment, or Room based on which model type they were being saved as. The story asked to be able to save any one of the three types all from the same form. My first idea was attempting to overload the POST method, dependent on which parameters were being passed into the method, but that unfortunately resulted in an ambiguous error. I also attempted adjusting the binding prefixes, but was having issues with the view model the page was using to display the different inherited classes. Due to time and considering I was already using jQuery to disable form inputs depending on which type of rental was being saved, I ultimately added two more methods and had jQuery adjust the POST url to target the corresponding controller method. If I had more time within the sprint, I would absolutely go back in to refactor and consolidate the multiple methods into just one.

## Skills Learned
* Better understanding of C#
* Better understanding of ASP.NET MVC
* Better understanding of AJAX, jQuery, JSON
* Working with pre-determined aesthetics and templates
* More efficiently communicating approaches to code
* More efficiently researching appropriate solutions to road blocks
* Understanding code written by previous developers
