Backbonejs
==========

Backbone JS experiment - Experimentation with Backbone.js

Things to remember:

1. Initialize Method: Called when a new instance of a model is created. (Pg:29)
2. Default Property: Set default values in your Model using Defaults property.
3. Model.get(): Provides an easy access to a Model's attributes. Get singles values such as
	console.log(todo2.get('title'));
4. toJSON() Method: Read or clone all of a model’s data attributes, use its toJSON() method. Returns a copy of the attributes as an object. Not an JSON string.
5. JSON.stringfy() : Returns the value as a string instead of an object.
6. Model.set(): Sets a hash containing one or more attibutes on the model. When attributes change the state of the model through Model.Set(), it triggers change events. Ex: change:name, change:age.
7. Model exposes an .attributes attribute - internal hash containing the state of an model. JSON object. Used to set values. Bypasses the triggers bound to the model.
8. slient:true - will silence events/ no events might be triggered. 
9. Add listeners: Add listeners to watch for the changes in the model in the initialize() method.
10. Model.validate(): Validation for Model. Allows for checking values prior to setting them. Model is validated when you use Model.set() or when you use Model.save()
11. Views in Backbone does not have the markup. Logic behind presentation of the model's user data to the user.
12. Views render method can be bound to Model's change event, so the changes are instant.
13. 




