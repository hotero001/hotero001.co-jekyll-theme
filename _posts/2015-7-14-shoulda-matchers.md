---
layout: post
title: Shoulda matchers
---

Today I was introduced to yet another time-saving feature of Rails: Shoulda matchers. Shoulda matchers are simple 
one liner tests for Rails. Shout out to the wonderful dudes/dudettes at Thoughtbot for this functionality.

To use shoulda-matchers, the gem must first be installed. Open your gem file and include the following lines:

=====GEMFILE=====
{% highlight ruby linenos %}
group :test do
  gem "shoulda-matchers"
end
{% endhighlight %}

Now, run the following command on your terminal to install the gem:

{% highlight ruby linenos %}
$bundle
{% endhighlight %}

Now let's replace the existing test below with shoulda matchers.

{% highlight ruby linenos %}
describe Category do
  it "has many videos" do
    comedies = Category.create(name: "comedies")
    silicon_valley = Video.create(title: "Silicon Valley", description: "Funny start-up life", category: comedies)
    simpsons = Video.create(title: "The Simpsons", description: "Animated life", category: comedies)
    expect(comedies.videos).to eq([silicon_valley, simpsons])
  end
end
{% endhighlight %}

Using shoulda matchers we can accomplish the same test above using only the lines below

{% highlight ruby linenos %}
describe Category do
  it { should have_many(:videos) }
end
{% endhighlight %}

As you can see, we can reduce the amount of code we write during testing by using shoulda matchers. You can check 
out http://matchers.shoulda.io/ for documentation and other examples. Thanks for reading.
[http://matchers.shoulda.io/](http://matchers.shoulda.io/)

