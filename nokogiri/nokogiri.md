!SLIDE center 
![Nokogiri](nokogiri.png)

!SLIDE bullets incremental
# What is Nokogiri?#
* An HTML/XML reader that parses out information in a useable format
* Can search the Nokogiri data using xpath or css selectors
* Let's install it

!SLIDE commandline incremental
	$sudo gem install nokogiri
	Building native extensions.  This could take a while...
	Successfully installed nokogiri-1.4.4
	1 gem installed
	Installing ri documentation for nokogiri-1.4.4...
	Installing RDoc documentation for nokogiri-1.4.4...

!SLIDE bullets incremental
## If you use Nokogiri you will use xpath extensively. Here are some basics for selecting info:##
* Selects the root node => /
* Selects all in the document that match => //
* Selects the current node => .
* Selects the parent of the current node => ..
* Selects attribute => @

!SLIDE center incremental
## For a good tutorial on xpath: ##
## http://www.w3schools.com/xpath/default.asp ##

!SLIDE center incremental
## Time for an example ##
.aside and maybe some *witchcraft*

!SLIDE
## Xpath example ##
	@@@ Ruby
	require 'nokogiri'
	require 'open-uri'
	website = 'http://scholar.google.com/etc'
	doc = Nokogiri::HTML(open(website))
    doc.xpath('//h3/a').each do |title|
	  puts title.text
	end

!SLIDE
## CSS example ##
	@@@ Ruby
	require 'nokogiri'
	require 'open-uri'
	website = 'http://scholar.google.com/etc'
	doc = Nokogiri::HTML(open(website))
	doc.css('.gs_rt a').each do |title|
		puts title.text
	end
	
!SLIDE
## CSS with regex example ##
	@@@ Ruby
	require 'nokogiri'
	require 'open-uri'
	website = 'http://scholar.google.com/etc'
	doc = Nokogiri::HTML(open(website))
	doc.css('font .gs_fl').each do |title|
		puts title.text[/[0-9\.]+/]
	end
	
	

