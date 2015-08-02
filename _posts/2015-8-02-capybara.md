---
layout: post
title: Intro to Behavior Driven Development, Capybara
---

Capybara is a web-based automation framework used for creating functional tests that simulate how users would interact with 
your application. There are a few alternatives, but Capybara has gained a lot of popularity in the Ruby on Rails community. 
Below is an example of testing with Capybara using Rspec. I have chosen Capybara using Rspec because I am most familiar with 
the Rspec testing framework, but Capybara can also be used with Test::unit.

{% highlight ruby linenos %}
feature 'User signs in' do
  background do
    User.create(username: "john", full_name: "John Doe")
  end
  scenario "with existing username" do
    visit root_path
    fill_in "Username", with: "john"
    click_button "Sign in"
    page.should have_content "John Doe"
  end
end
{% endhighlight %}

Our app is a simple log in page that has a text input for a username, followed by a Sign in button. The code we have written 
above creates a username "John Doe" and in the scenario block we test the app by filling in the text input with "john" and then 
signing in. We then assert that the page should have a username of "John Doe". 

{{hotero001.github.io/images/404.jpg}}
