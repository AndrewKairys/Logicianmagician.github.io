---
layout: post
title:      "CLI - Project and Process"
date:       2018-05-04 14:50:22 +0000
permalink:  cli_-_project_and_process
---


  This will be the first Command Line Interface that I've built from scratch, so I had a few goals I wanted my CLI to accomplish. One, it needed to be able to return essentially recipe cards with the nutritional values so that someone could then assess if that dish was right for them. Two, it needed to scrape the correct information and store it within each dish object I created so that it could be returned easily by my interface to the human on the other end. Third it needed to not break from any input outside of the interface prompts. 

  So I first created my CLI so that upon starting the application it would be easily readable in the terminal format. I used some tilde characters to cleanly delineate prompts and answers. Once you enter which format you'd like to receive your initial information in List or Random, you are then asked the type of dish you'd like to see: Meal, Treat, Snack, or Drink. Once you select a type of dish you'll be given a sample of 10 dishes that fit that type. You're then prompted to enter which number you'd like to see more about, you're then given a nutritional snippet of the dish's: Calories, Fat, Protein, Net-Carbs, and the recipe URL. I wanted the user to be able to explore the dish further by prompting them if they'd like to view the recipe in their browser. It then takes them to that dish's ingredient list, and recipe. This way you'll know for sure if that's a ketogenic dish that would fit their goals.
	
	The Scraper class was simple in that it only has two methods, but complex in that pinpointing the information you want your objects to be instantiated with from the Nokogiri Document. I broke down the Document into each "card" element, then iterated over each element to create an object with the appropriate instance variables to store the data I'd need for later. I then had each dish save itself to a Dish class container where I pulled my recipe information. It was then just a matter of selecting the correct dish types and presenting them to the user.
	
	Creating a CLI application that won't break from bad input should be top priority once you've got most of your app working, to accomplish that I had two methods to do this, one for each output choice. Below I used this dish_by_type method to return the correct type of dish objects
I've always enjoyed the case method for it's readability, I fed this method input that had been converted to all lowercase characters, and it will only accept an available type of dish. Or it will let the user know it doesn't understand the input, and restart the CLI application. When in list output there's another layer that needs to be verified as safe to use so I made a dish_list_helper method that only takes in numbers 1-10 and restarts the app if the input can't be handled.


Please check out my project on my Github: [KetoDish-CLI-App](https://github.com/AndrewKairys/GetDish-cli-app)
