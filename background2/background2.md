!SLIDE bullets incremental
## That wasn't so hard... What's next?##

!SLIDE bullets incremental
##ICES uses a recruiter site for its experiments that facilitates:##

* Students signing up for experiments
* Researchers managing experiments
* Details of subjects and past experiments

!SLIDE bullets incremental
# Task #2#
* Find a replacement for the ICES recruiter (ORSEE)
* Scrape all the current data from our recruiter
* Put that data into ORSEE

!SLIDE center incremental
## We saw how to scrape data so this shouldn't be so tough... ##

!SLIDE center
## The data on the recruiter isn't publicly available ##
## and can only be accessed by people signed in ###

!SLIDE center
## Looks like we need a new tool that will allow us to enter and submit form information into websites, follow links, and click buttons...##

!SLIDE center
## Sounds like a job for MECHANIZE!##
![Background](mechanize.png)
##http://mechanize.rubyforge.org/mechanize/##

!SLIDE center
## Let's look at some real examples... ##

!SLIDE 
## Sample Mechanize Code ##
	@@@ Ruby
	require 'mechanize'
	agent = Mechanize.new
	agent.get(website)
	agent.page.forms
	agent.page.links
	agent.page.forms.submit
		

