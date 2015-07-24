---
layout: post
title: Writing Controller Tests
---

Controller specs are typically categorized by actions (ie index, new, create, etc.). This week I started learning how to write 
controller tests. Here is an example of one from my test app below.

{% highlight ruby linenos %}
class TodosController < ApplicationController
  def index
    @todos = Todo.all
  end
  
  def new
    @todo = Todo.new
  end
  
  def create
    @todo = Todo.new(params[:todo])
    if @todo.save
      redirect_to root_path
    else
      render :new
    end
  end
end
{% endhighlight %}

{% highlight ruby linenos %}
require 'spec_helper'

describe TodosController do
  describe "GET index" do
    it "sets the @todos variable" do
      cook = Todo.create(name: "cook")
      sleep = Todo.create(name: "sleep")
    
      get :index
      assigns(:todos).should == [cook, sleep]
    end
    
    it "renders the index template" do
      get :index
      response.should render_template :index
    end
  end
end
{% endhighlight %}

