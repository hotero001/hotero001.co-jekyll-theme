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
  
  describe "GET new" do
    it "sets the @todo variable" do
      get :new
      assigns(:todo).should be_new_record
      assigns(:todo).should be_instance_of(Todo)
    end
    
    it "renders the new template" do
      get :new
      response.should render_template :new
    end
  end
  
  describe "POST create" do
    it "creates the todo record when the input is valid" do
      post :create, todo: {name: "cook", description: "Enjoy cooking"}
      Todo.first.name.should == "cook"
      Todo.first.description.should == "Enjoy cooking"
    end
    
    it "redirects to the root path when the input is valid" do
      post :create, todo: {name: "cook", description: "Enjoy cooking"}
      response.should redirect_to root_path
    end
    
    it "does not create a todo when the input is invalid" do
      post :create, todo: {description: "Enjoy cooking"}
      Todo.count.should == 0
    end
    
    it "renders the new template when the input is invalid" do
      post :create, todo: {description: "Enjoy cooking"}
      response.should render_template :new
    end
  end
end
{% endhighlight %}

