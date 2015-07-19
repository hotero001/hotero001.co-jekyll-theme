---
layout: post
title: Javascript Testing w/Jasmine
---

I recently completed the Javascript Testing course offered by Udacity. On the course page, it estimates 2 weeks to 
complete the course, but it can be completed in one sitting of a few hours. Seriously. The course is an introduction to 
testing javascript applications using the red-green-refactor workflow. The course goes over testing using the Jasmine 
testing framework. I decided to take the course because I have recently started learning about testing in Ruby on Rails 
applications, and I wanted to get a taste of what testing is like on other platforms. As a Ruby on Rails developer, 
testing Javascript apps seems the most pragmatic option. I learned that testing Javascript apps is very similar to testing 
Ruby on Rails apps. The Udacity course uses the same red-green-refactor workflow that most Ruby on Rails developers advocate. 
Also, similar to Rails testing in Rspec, a Javascript test begins with an 'it' declaration and ends with the 'expect' 
declaration for what the expected test outcome should or should not be. Here is one of the tests that was covered in 
the course.

=====AddressBookSpec.js=====

{% highlight ruby linenos %}
describe ('Address Book', function() {
    var addressBook,
        thisContact;
        
    beforeEach(function() {
        addressBook = new AddressBook();
        thisContact = new Contact();
    });
    
    it('should be able to add a new contact', function() {
        addressBook.addContact(thisContact);
        
        expect(addressBook.getContact(0)).toBe(thisContact);
    });
});
{% endhighlight %}

=====AddressBook.js=====

{% highlight ruby linenos %}
function AddressBook() {
    this.contacts = [];
}

AddressBook.prototype.addContact = function(contact) {
    this.contacts.push(contact);
}

AddressBook.prototype.getContact = function(contact) {
    return this.contacts[index];
}
{% endhighlight %}

The example in AddressBookSpec.js above creates an empty AddressBook, and then populates it with a single Contact. The test 
then asserts that we should expect the only contact present in the AddressBook to be the Contact that we just added. With the 
functions that we have created in the AddressBook.js file, we get a passing test. The Udacity course, albeit very brief, has 
given me a good starting point for testing Javascript apps, and I recommend you check it out if you are new to testing Javascript 
apps. 
