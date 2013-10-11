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
10. Model.validate(): Validation for Model. Allows for checking values prior to setting them. Model is validated when you use Model.set() or when you use Model.save(). Triggers an 'invalid' event if the validation does not go through.
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

37. Underscore's chain method - .chain()
38. Chaining is a sequence of methods calls on the same object in a single statement.
Array manipulation methods of underscore can be applied on Collections objects, but they return arrays, so chaining is not possible. With the inculsion of .chain() you can apply methods that return objects.
39. The chain ends with a call to the .value() method, which simply returns the resulting array value.
40. When you apply an .chain() method you get back an array that you work with.
41. RESTFUL synchronization with a server through the simple API.
42. Collections.fetch() - Retrieves a set of models from the server in the form of a JSON array by sending an HTTP GET request to the URL specified in the collections url property.
43. Backbone can retrieve an entire collection with an HTTP GET request -.fetch() you can update only a single model using .save() method.
44. Save() can be used to the send the data to the server in case when the data was fetched from the server. The 'id' of the model is appended to the collections URL's and sent to the server by using HTTP PUT request.
	If the model is a newly created instance of the date then a HTTP POST is invoked to save the data on the server.
45. Collections.create() - this is used to create a new model, add it to the collection and send it to the server in a single method call.
46. Unlike Collection.remove(), which only removes a model from a collection, Model.destroy() will also send an HTTP DELETE to the collection’s URL.
47. Enabling {patch:true} with .save() on a Model will only update the new attributes/parital updates to the server instead of the entire Model contents.
48. {reset:true} option on the Collection.fetch() will update the Collection using reset() rathen than set().
49. Events are basic inversion of control. Function can call another function by name, the second function is registered as an handler that is called when an event has occured.
50. User interface does not need to know about Business logic works. 
51.	Backbone.Events give any object the ability to bind and trigger custom events.
52. There is no need for the events to be declared before being bound to a callback handler.
53. publish/subscribe - in this case 'on' is the subscribe and 'trigger' is publish.
54. on/off/trigger - trigger specified event or multiple list of events.
	ourObject.trigger("dance jump skip", 'very tired from so much action.');
	multiple arguments to the event.
	ourObject.trigger("dance jump skip", 'on fire', "15 minutes");
55. on,off events directly bind to the observed objects.
56. listenTo() - Lets an object to listen to events on another object.
56. stopListening() - Lets to stop listening to events.
57. Ghost View: A View is removed but the corresponding Model is not removed. Views are notified of changes in the Model. So, when a View is removed it has reference to Models which causes memory leak issues.
58. 'on' called on every object needs a corresponding 'off' call, wheras an stopListening() call would be sufficient for all listenTo() event.
59. View.remove() method calls .stopListening() event to make sure all the events are unbound before destroying the view. This helps with unregistering all the events.
60. View have two different type of events: DOM events, and event triggered using the API.
61. Can bind DOM events using jQuery's '.on' event or view's events property. jQuery- refers the DOM element, whereas the view's event refers to the view object.
62. Routers help you connect URL's to parts in your application.
63. Maps to a router to a function that decides what to do with it.
64. Function maps
	'route': 'mappedFunction'
65. HTML5 Push State: window.history.pushState
66. It is also possible for router.navigate() to navigate to the URL but trigger the function. This could be implemented by setting 
67. Backbone.history.start() - let's Backbone know to monitor haschange' events.
68. Backbone.sync - This is an integral part of Backbone.js. It is similar to jQuery's .ajax() method.
69. Can override Backbone.sync globally or at the Collection or Model level.
70. Backbone.sync= function( method, model, options){ }
	options - success or error methods.
71. DOM manipulation: jQuery or Zepto. Underscore.js OR Lo-Dash; json2.js - for legacy browser support for JSON.
72. 



