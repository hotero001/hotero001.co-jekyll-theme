---
layout: post
title: Rails Routing
---

In Rails, a resourceful route provides a mapping between HTTP verbs and URLs to controller actions. Each action maps to 
particular CRUD(Create, Read, Update, Delete) operations in a database. An entry in the routing file, such as: resources :photos 
creates seven different routes in your app, which map to the Photos controller:

photos#index===
photos#new===
photos#create===
photos#show===
photos#edit===
photos#update===
photos#destroy


