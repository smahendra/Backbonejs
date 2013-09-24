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
13. 'el' is a reference to a DOM element. 'el' composes all the markup required to be inserted into the DOM that avoids multiple reflows and repaints. This helps with improving the performance of the browser.
14. There are two ways to assocaite an DOM element.One is to create an element for the view itself or associate an element that is already present on the page.
15. New element in the View can use a combination of: tagname,id,and classsName.Nothing specified tagName is 'div'.
16. view.$el - $(view.el) 
	view.$(selector) - $(view.el).find(selector)

17. setElement - can be used to bind an View to different DOM element.
18. render() - Defines the logic for rendering an template.
19. _.template() - method complies Javascript templates into functions that can evaluated for rendering.
20. return this; - only to create the list once and avoiding repaints. Making views easily readable in other parents views.
21. event Hash - Allows you to attach events to the 'el' or el-relative selectors. Current view object within the call back function.  
	'eventName selector': 'callbackFunction'
22. Backbone uses jQuery's .delegate() method - further goes to extend and refers always to the current view object within call back function.
23. Backbone.Collections: Backbone are collection of set of models. 
24. One can add and remove models using .add() and .remove().
25. Adding models to a collection using {merge: true}, will merge the models () whereas the default will ingnore the models that comes at last.
26. Models as objects are passed by reference.
27. Collection.get() - this is a way to get an model from a Collection.
28. id, cid, idAttribute
When Model is created Backbone assigns/ automatically generates it a id called as client id (cid). This happens when data is not stored yet to the server.
30. id - is either an integer or a string that is defined for the Model (usually by user).
31. idAttribute - is the indentifying attribute of the Model returned by the Server.This is set by the Server. For example use it anytime when you want to use other forms as id's.
32. once() method - Call the call back function only once for a change.
33. Collection.reset() - Reset the entire collection. This will replace the contents of the Collection.You can use .reset() without any arguments to completly reset the Collection.One can listen to reset() events as we do with change events.
34. options.previousModels - Can be used with Collection.reset() to get hold of the previous models that are defined.
35. update() method - This is available for Collections to update the models present in a collection. If there are new models an add event is triggered/ remove - for remove models, and if there are conflicts they are merged accordingly.
36. Underscore utility functions: Avilable on Collections.
	.forEach: Loop through the Collections to get the models/ attributes.
	.sortBy(): Sort a collection on a specific attribute
	.map(): Create a new collection by mapping each value in a list through a transformation function
	.min()/.max(): Retrieve item with the min or max value of an attribute. For example try this on 'id'
	pluck(): Extract a specific attribute.
	filter(): Filter by an array of model IDs.
	indexOf(): Return the item at a particular index within a collection
	.any()/ .some() :  Confirm if any of the values in a collection pass an iterator truth test
	size(): Return the size of a collection
	isEmpty(): Determine whether a collection is empty

	**** Operations on Models now
Operations on object are aviable as methods on Models.
	pick(): Extract a set of attributes from a model.
	omit(): Extract all attributes from a model except those listed.
	keys() and values(): Get lists of attribute names and values
	pairs(): Get list of attributes as [key, value] pairs
	invert(): Create object in which the values are keys and the attributes are values

	
	




