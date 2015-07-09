---
layout: post
title: Glimpse of TDD
---

This week I continued my journey on Tealeaf Academy's Ruby on Rails online bootcamp. Students have been asked to test the video model and category model and associations 
in the Netflix clone web application that we are in the progress of building. I have practiced TDD in the past, but only as practice exercises, 
never in the context of an actual web application. Tealeaf Academy's testing is taught using rspec, which I am unfamiliar with. In past practice 
exercises, I have written TDD tests using Minitest unit tests. So this is yet another thing I will have to commit to memory. We start by including 
rspec in the gemfile for both test and development mode as follows:

{% highlight ruby linenos %}
group :test, :development do
  gem 'rspec-rails'
end
{% endhighlight %}

After this, we run the following commands on the terminal:

{% highlight ruby linenos %}
$bundle
$rails g rspec:install
{% endhighlight %}

And, here is our video model:

=====Video model=====

{% highlight ruby linenos %}
class Video < ActiveRecord::Base
  belongs_to :category
end
{% endhighlight %}

Now we can create a spec to test the video model. 

=====Tests=====

{% highlight ruby linenos %}
require 'spec_helper'

describe Video do
  it "saves itself" do
    video = Video.new(title: "Y Tu Mamá También", director: "Alfonso Cuarón", synopsis: "Coming of age")
    video.save
    expect(Video.first).to eq(video)
  end
end
{% endhighlight %}

Now, we can go back to the terminal and run the following commands:

{% highlight ruby linenos %}
$rake db:test:prepare
$rspec
{% endhighlight %}

Line one directly above is required to bring the test database to the same schema structure as the development database, since tests 
run on a seperate database as the development database. Without running the first line on the terminal, the tests will fail. The result of the test 
is 1 example and 0 failures.

Yay! We have written our first successful test using Rspec. For sake of brevity, I will leave out the tests for the category model and 
associations. Also, the example test above is not something we would actually test for in an application since it does not test any of the code we have written but rather tests Rails itself. I have simply included it as an example.
