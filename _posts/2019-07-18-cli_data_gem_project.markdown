---
layout: post
title:      "CLI Data Gem Project"
date:       2019-07-18 18:52:26 +0000
permalink:  cli_data_gem_project
---

Hello my name is Candice. In this post, I will describe step-by-step how to build a CLI gem.
I love shopping for shoes.  However, when it comes to getting my sons the latest and greatest Lebron James Nike shoes, it can be pretty expensive. I created a gem that would allow the user to check out prices for popular Nike shoes. The user is able to search by name and price, then make a selection and see the description and url where they can see photos and sizes available on the Nike site. As a consumer, it's good way to comparison shop. See what the manufacturer prices are before going to the popular stores like Foot Locker.

This is a simple scraper which gives the names and prices of men's Nike shoes,  description of the shoes selected, and a url so you can see photos and available sizes. 
So here are some useful tips I used to built my CLI gem.

1. Install Bundler Gem

Save time and go with Bundler Gem! The setup was simple and very efficient. Perfect for a beginner. A good resource is Bundler (https://bundler.io).

Create a ruby gem using Bundler, use the command syntax  such as:

bundle gem <name of your project>

2. Add executable file

I added an executable file gem's files and placed it in my bin directory. The files in bin are all files that help to run my program and always begin with a shebang line #!usr/bin/env ruby. This tells my shell or bash to interpret the file as ruby to run it.

Here's an example:


Before you can run  your file using ./bin/<file_name> you might be prompted with permissions. Use ls-lah to list all the files in the current directory. Make your file executable by using chmod.

$chmod +x <file_name>

3. File requirements

In order to require gems, I added files to environment.rb. All the files I need to run my program will be located inside my environment folder and sent to my bin at run time.

4. Gemspec Folder

The gemspec specifies the information about a gem such as its name, version, description, authors and homepage. I add any dependencies such as "Nokogiri". Make sure to update this in you gemspec. You may get some errors or have trouble running your program you forget to add it.

5. Write CLI

After setting up my environment, I was ready to write to write some CLI and scrape. After watching a how to video on creating a CLI gem. I learned that it's best to set up my CLI and class files first then scrape. I created a call method on my CLI page that basically ran my entire program. I first started with pseudo code just to make sure things were at least working as it should. It was a pretty good strategy. With each update I would run my program to debug. Once I set up my Shoe class, it was time to scrape.

I ended up scraping nike.com which was not as easy to scrape as I thought. First, I had trouble just opening the page. I won't share how I actually got in, but know I eventually did. I scraped the entire unit in one method which made it easier to debug if I needed to in the future.

The thinking process I used helped me to build my scraper method. 

Create a class method using the self. syntax that refers to the entire class itself. For example, I named my class method  self.get_page because I used the Nokogiri gem and open-uri to send an http request to nike.com and Nokogiri parsed the requested http so I could began scraping.

I used css selectors such as < div class = "product-name" and  < div class = "price" to get name  and price instances for my Shoe class, and attached the scrapes to variables such as name= "name _of _shoes and price = price_ of shoes.  I iterated my instances using the doc variable that set equal to my scraper url. In other words I called .css on doc (doc.css) used a temporary placeholder "item" , so the elements from the arrays I scraped could pass through. I had .css now call on the placeholder "item" (item.css) and this is how my shoe instances were created for iteration.

#first scrape
class CliProject::Scraper
  
  def self.get_page
      doc = Nokogiri::HTML(open("https://store.nike.com/us/en_us/pw/mens-nikeid-lifestyle-shoes/1k9Z7puZoneZoi3",'User-Agent' => 'ruby'))
    doc.css(".grid-item.nikeid").each do |item|
    name = item.css(".product-name").css("p").text
    price = item.css(".product-price").css("span.local").text
    url = item.attr("data-pdpurl")
    CliProject::Shoe.new(name, price, url)
      end
   end
end
 
 Once the instances were iterated by my each method, they were ready to be instantiated and saved by the Shoe class.
Now that I had real object instances I could get rid of my psuedo code. Since, my CLI and Shoe class were created previously I could debug see the results of my first CLI scrape. This was the result of collaborating my scraper to my shoe class and then both classes to my CLI.  Sorry there are no pictures, but I need to figure out how to do it. In order to compensate for the lack there of I tried to be a specific as possible. 

To see my complete code for my CLI gem please visit my repository page on GitHub at https://github.com/lexus2727/cli_project .












