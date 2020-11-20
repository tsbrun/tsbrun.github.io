---
layout: post
title:      "Writing tests with RSpec"
date:       2020-11-20 20:45:04 +0000
permalink:  writing_tests_with_rspec
---


I finally sat down to learn RSpec! I found a simple RSpec tutorial on the website [sempahoreci.com](https://semaphoreci.com/community/tutorials/getting-started-with-rspec).

Initially, I was intimidated to learn how to write tests because I thought it would be a difficult process. Thankfully, though, RSpec is fairly semantic and straightforward. 

First, you need a `describe` block. It takes either a class name or a string. The tutorial used the class name `StringCalculator`, since it instructs you to build a calculator as an example app for testing. 

Next, you need `context` blocks. They are technically identical in function to `describe` blocks. However, you use them within a `describe` block to give, well... *context* to whatever test you're writing. For example, 

<code style="color:blue">
  describe StringCalculator do<br>
	  context ".add" do<br>
		end<br>
	end<br>
</code>

The `context` block explains that you are writing tests for the class method ".add". 

Now, to write an actual test, you have to define your *expectation* (more on that later) within an `it` block—**it** being the thing you're testing, as described by `describe` and `context`.

<code style="color:blue">
  describe StringCalculator do<br>
	  context ".add" do<br>
		context "given an empty string" do<br>
		it "returns 0" do<br>
		end<br>
		end<br>
		end<br>
	end<br>
</code>

The `it` block contains the test case, in which an **expectation** is defined. According to the [RSpec docs](https://relishapp.com/rspec/rspec-expectations/docs), expectations define expected outcomes. If you expect the .add method to return 0 when given an empty string, you would write that test as follows:

<code style="color:blue">
expect(StringCalculator.add("")).to eq(0)
</code>

And there you have it—your (my) first RSpec test! 

Depending on what's in the StringCalculator class, either your test could fail and RSpec displays the context strings along with expected and actual input, *or* the test passes. 

RSpec has different [matchers](https://relishapp.com/rspec/rspec-expectations/v/3-9/docs/built-in-matchers) that you can use to define what kind of behavior you expect from your program. The documentation is very clear, easy to read, and RSpec itself is much easier to get the hang of than I thought it would be. 

My next mission is to master Capybara! 

![](https://media.giphy.com/media/ck0RCabAX6VUDCTywd/giphy.gif)
