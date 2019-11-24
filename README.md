# ideal objects Spec

## Overview

This spec defines a way for creating objects that will work in any [ideal objects](http://idealobjects.net/) system. The goal is to create enough of a standard to promote interoperability, but to give the creator as much flexibility as possible.

Each example in this document is in Javascript Object Notation (JSON). Initial systems may be build using this notation, but should not be the limiting factor. Other formats, such as YML and XML, should be possible implementations.

## Objects

An object is a thing. It could be a person. Or the bike they ride. A coffee bean, or a cup of coffee. An object is any thing that you want to represent as a piece of data in your system. They are the [atoms](https://www.livescience.com/37206-atom-definition.html) of any programming system.

## Properties

Each object has a specific set of properties, or attributes, that represent them. Your bike might be blue, whereas mine is red.

We don't worry too much about how you define a bike color, that is up to you. There are a few properties that are required.

### Required Properties

These are properties that the ideal object systems expect. Without them, your objects might not work.

#### ID

Add to any object as a property named *_id*.

This is a unique identifier for the system -- the SSN of your object. No two objects should have the same ID. If they do, they may end up overwriting each other.

#### Type

Add to any object as a property named *_type. 

This is the type of object. As a default, you can define everything as "io.object". You can use any object name that you would like in your system. This is a good way to classify objects. For example, a person might be "sys.person" whereas a bike might be "sys.bike".

The type should act as a loose requirement to what other properties should be added to the object. This will not be required, but could have restrictions in certain systems that will reject your object if it doesn't have the properties that the type defines.

#### Space

Add to any object as a property named *_space*.

Space is a loose requirement. It is not necessarily required, but is used to identify where the object will be saved, or where it currently lives. If the system you are working in does not incorporate spaces, then this can be ignored.

## Linking

Objects become much more powerful when you can link them together. For example, you will want to linked to your bike as it's owner. In your system, you will want these objects linked instead of creating multiple copies.

Linking is a core property of [hypermedia](https://www.techopedia.com/definition/3105/hypermedia), which is another reason why object linking is provided. Without an ideal object system, you can still publish your objects on the internet and link them together.

## Nesting

Nesting is not expeted or defined in this initial spec. Support for this may be required as a system or spec extension. The expectation is that you use linking instead.


## Examples

```JSON
{
  "_id": "Dave",
  "_type": "io.object",
  "height": "5-5",
  "job": "Grocer"
}
```
