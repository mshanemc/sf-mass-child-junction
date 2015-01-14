sf-mass-child-junction
======================


In my example, I have a questionnaire, and a list of potential questions.  User can build the questionnaire by joining the pre-built questions to the questionnaire using this junction object (questionnaire item).

![Junction Object diagram](https://dl.dropboxusercontent.com/s/f0jsueg62xl6ohw/junction%20object%20sample.png?dl=0)

So obviously re-using the questions saves the user work, but the process of adding questions is kinda clunky.  

* Click on the Add Questionnaire Item button
* Click on the lookup dialog button
* Search Question Texts (hopefully you know them all by heart!)
* Save
* Repeat--for maybe a few dozen questions?

So what I made was a visualforce page to list all the optional questions, check their boxes, and then hit the add button.


###New Version
see the page called ![MassChildJunctionAddParameterized](https://github.com/mshanemc/sf-mass-child-junction/blob/master/src/pages/MassChildJunctionAddParameterized.page)



###Older Version 
(see the page called ![MassChildJunctionAdd](https://github.com/mshanemc/sf-mass-child-junction/blob/master/src/pages/MassChildJunctionAdd.page))
![Mass Add Questions Page](https://dl.dropboxusercontent.com/u/8451460/salesforce%20blog/Mass%20Child%20Junction%20Add.png)

For nicety, I did these using some of the standard VF components (pageblock, buttons, etc).  You probably won't want to do that if your intent is to do this in the Salesforce1 mobile app.

All the code is on github.  I used angularJS, connected to Salesforce by a lovely package called [ngforce](https://github.com/noeticpenguin/ngForce) written by [MVP Kevin Poorman](https://twitter.com/codefriar).  My github repo contains a packaged-up-version of ngforce saved as a static resource if you'd like to play with it quickly.

To load the page, there's a custom button I added
![Custom Button Config](https://dl.dropboxusercontent.com/u/8451460/salesforce%20blog/mass%20add%20questions%20button.png)

You can then drop it onto the questionnaire (original parent) layout.  It takes the recordId from the questionnaire which is then used to populate the children.
