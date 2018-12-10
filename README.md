[![npm](https://img.shields.io/npm/v/WiredPanels.svg)](https://www.npmjs.com/package/WiredPanels)
[![Build Status](https://secure.travis-ci.org/Symatem/WiredPanels.png)](http://travis-ci.org/Symatem/WiredPanels)
[![semantic-release](https://img.shields.io/badge/%20%20%F0%9F%93%A6%F0%9F%9A%80-semantic--release-e10079.svg)](https://github.com/Symatem/WiredPanels)
[![GitHub Issues](https://img.shields.io/github/issues/Symatem/WiredPanels.svg?style=flat-square)](https://github.com/Symatem/WiredPanels/issues)
[![Dependency Status](https://david-dm.org/Symatem/WiredPanels.svg)](https://david-dm.org/Symatem/WiredPanels)
[![devDependency Status](https://david-dm.org/Symatem/WiredPanels/dev-status.svg)](https://david-dm.org/Symatem/WiredPanels#info=devDependencies)
[![downloads](http://img.shields.io/npm/dm/WiredPanels.svg?style=flat-square)](https://npmjs.org/package/WiredPanels)
[![Greenkeeper badge](https://badges.greenkeeper.io/Symatem/WiredPanels.svg)](https://greenkeeper.io/)

# Features

-   Framework to build an Editor or Visualizer
-   No dependencies / no bloatware
-   Elements: Panels, sockets and wires
-   Configure: Many customizable options & parameters
-   Rendering
    -   SVG
    -   CSS animations
    -   Automatic layout inside panels (depending on text width)
    -   Force layout and overlap avoidance between panels
-   Mouse controls
    -   Touch event handlers for mobile use
    -   Move panels
    -   Drag / draw wires
    -   Selection: Click, Shift Invert, Box
-   Keyboard controls
    -   Enter: Use / Activate
    -   Backspace: Delete
    -   Meta (+ Shift) + Z: Undo & Redo
    -   Meta + A: Select all panels

# API

<!-- Generated by documentation.js. Update this documentation by updating the source code. -->

### Table of Contents

-   [Wire](#wire)
    -   [Properties](#properties)
-   [Panel](#panel)
    -   [Properties](#properties-1)
-   [Socket](#socket)
    -   [Properties](#properties-2)
-   [WireDragCallback](#wiredragcallback)
    -   [Parameters](#parameters)
-   [WireConnectCallback](#wireconnectcallback)
    -   [Parameters](#parameters-1)
-   [ActivateCallback](#activatecallback)
    -   [Parameters](#parameters-2)
-   [RemoveCallback](#removecallback)
    -   [Parameters](#parameters-3)
-   [CopyCallback](#copycallback)
    -   [Parameters](#parameters-4)
-   [PasteCallback](#pastecallback)
    -   [Parameters](#parameters-5)
-   [WiredPanels](#wiredpanels)
    -   [Parameters](#parameters-6)
    -   [Properties](#properties-3)
    -   [createWire](#createwire)
        -   [Parameters](#parameters-7)
    -   [createPanel](#createpanel)
        -   [Parameters](#parameters-8)
    -   [createSocket](#createsocket)
        -   [Parameters](#parameters-9)
    -   [updatePanelSockets](#updatepanelsockets)
        -   [Parameters](#parameters-10)
    -   [updatePanelGeometry](#updatepanelgeometry)
        -   [Parameters](#parameters-11)

## Wire

Type: [Object](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Object)

### Properties

-   `type` **[string](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String)** ='wire'

## Panel

Type: [Object](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Object)

### Properties

-   `type` **[string](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String)** ='panel'
-   `sockets` **[Array](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Array)&lt;[Socket](#socket)>** 
-   `springs` **[Map](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Map)** 

## Socket

Type: [Object](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Object)

### Properties

-   `type` **[string](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String)** ='socket'
-   `wiresPerPanel` **[Map](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Map)** 

## WireDragCallback

Type: [Function](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Statements/function)

### Parameters

-   `socket` **[Socket](#socket)** 

Returns **[boolean](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Boolean)** true if drag action should start

## WireConnectCallback

Type: [Function](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Statements/function)

### Parameters

-   `socket` **[Socket](#socket)** 
-   `wire` **[Wire](#wire)** 

Returns **[boolean](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Boolean)** true if connect action should succeed

## ActivateCallback

Type: [Function](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Statements/function)

### Parameters

-   `selection` **[Set](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Set)** 

## RemoveCallback

Type: [Function](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Statements/function)

### Parameters

-   `selection` **[Set](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Set)** wires and panels to be removed

Returns **void** 

## CopyCallback

Type: [Function](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Statements/function)

### Parameters

-   `clipboardData` **[Object](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Object)** 

Returns **[boolean](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Boolean)** true if data was copied

## PasteCallback

Type: [Function](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Statements/function)

### Parameters

-   `clipboardData` **[Object](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Object)** 

Returns **[boolean](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Boolean)** true if data was accepted and can be pasted

## WiredPanels

Container holding the graph of panels and wires

### Parameters

-   `config` **[Object](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Object)**  (optional, default `{}`)
    -   `config.socketRadius` **[number](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Number)** 
    -   `config.verticalSocketsOutside` **[boolean](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Boolean)** 
    -   `config.horizontalSocketsOutside` **[boolean](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Boolean)** 
    -   `config.wireStyle` **[string](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String)** 
    -   `config.panelCornerRadius` **[number](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Number)** 
    -   `config.panelPadding` **[number](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Number)** 
    -   `config.panelMargin` **[number](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Number)** 
    -   `config.springLength` **[number](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Number)** 
    -   `config.springStiffness` **[number](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Number)** 
    -   `config.panelCollision` **[boolean](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Boolean)** 
    -   `config.borderCollision` **[boolean](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Boolean)** 
    -   `config.undoActionLimit` **[number](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Number)** number of actions that can be undone
-   `eventListeners` **[Object](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Object)**  (optional, default `{}`)
    -   `eventListeners.wireDrag` **[WireDragCallback](#wiredragcallback)** 
    -   `eventListeners.wireConnect` **[WireConnectCallback](#wireconnectcallback)** 
    -   `eventListeners.activate` **[ActivateCallback](#activatecallback)** 
    -   `eventListeners.remove` **[RemoveCallback](#removecallback)** 
    -   `eventListeners.copy` **[CopyCallback](#copycallback)** 
    -   `eventListeners.paste` **[PasteCallback](#pastecallback)** 

### Properties

-   `panels` **[Set](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Set)** 
-   `springs` **[Set](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Set)** 
-   `wires` **[Set](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Set)** 
-   `selection` **[Set](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Set)** 
-   `config` **[Object](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Object)** 

### createWire

Create a new wire

#### Parameters

-   `wire` **[Object](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Object)** skeleton wire (optional, default `{}`)

Returns **[Wire](#wire)** wire

### createPanel

Create a new panel

#### Parameters

-   `panel` **[Object](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Object)** skeleton panel (optional, default `{}`)

Returns **[Panel](#panel)** panel

### createSocket

Create a new socket

#### Parameters

-   `socket` **[Object](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Object)** skeleton socket (optional, default `{}`)

Returns **[Socket](#socket)** socket

### updatePanelSockets

#### Parameters

-   `panel` **[Panel](#panel)** 

### updatePanelGeometry

#### Parameters

-   `panel` **[Panel](#panel)** 

# Examples

[Try online](http://symatem.github.io) with [source code](https://github.com/Symatem/symatem.github.io/blob/master/js/OntologyEditor.js)
