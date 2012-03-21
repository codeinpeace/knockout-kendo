---
layout: default
prefix: ../
name: NumericTextBox
description: The NumericTextBox widget allows for editing a variety of numeric value types.
docs: http://demos.kendoui.com/web/numerictextbox/index.html
examples:
    - title: Basic Example
      description: This example demonstrates passing a single option to bind against the value of the NumericTextBox widget.
      view: |
        <input data-bind="kendoNumericTextBox: price" />
        <hr/>
        Price: <strong data-bind="text: price"> </strong>
      js: |
         var ViewModel = function() {
            this.price = ko.observable(10.50);
         };
      selected: true
      id: one
    - title: Passing additional options
      description: This example demonstrates passing additional options in the data-bind attribute with *value* now being explicitly specified.
      view: |
        <input type="checkbox" data-bind="checked: enabled" /> Enabled<br/>
        <hr/>
        <input data-bind="kendoNumericTextBox: { value: price, enabled: enabled, min: 0, max: 100, format: 'c' }" />
        <hr/>
        Price: <strong data-bind="text: price"> </strong>
      js: |
         var ViewModel = function() {
            this.price = ko.observable(10.50);
            this.enabled = ko.observable(true);
         };
      id: two
    - title: Using global options
      description: This example demonstrates setting global options in *ko.bindingHandlers.kendoNumericTextBox.options*. This helps to simplify the markup for settings that can be used as a default for all instances of this widget.
      view: |
        <input type="checkbox" data-bind="checked: enabled" /> Enabled<br/>
        <hr/>
        <input data-bind="kendoNumericTextBox: { value: price, enabled: enabled }" />
        <hr/>
        Price: <strong data-bind="text: price"> </strong>
      js: |
         var ViewModel = function() {
            this.price = ko.observable(10.50);
            this.enabled = ko.observable(true);
         };
         
         ko.bindingHandlers.kendoNumericTextBox.options = {
            min: 0,
            max: 100,
            format: 'c'
         };
      id: three
      
liveOptions:
    - name: enabled
      description: Determines if users can interact with the field
    - name: value
      description: The current value of the field
    - name: widget
      description: If specified, will populate an observable with a reference to the actual widget

futurePlans:
---

{% include widget.html %}