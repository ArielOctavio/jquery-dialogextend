## NOTICE ##
```
Dear all,


The DialogExtend project has been moved to GitHub.

You could get the latest update at [https://github.com/ROMB/jquery-dialogextend]

Please allow me to express my thanks to ROMB who help to move this project forward.

This GoogleCode page will be kept for archive purpose.


God bless the community. :D
```



---



## Release ##
  * Version 1.0.1



## Compatible ##
  * jQuery 1.7.2
  * jQueryUI 1.8.22



## Overview ##
  * Neat, simple, and **ABSOLUTELY** unobtrusive
  * Extending (instead of replacing) original jQuery UI dialog
  * Maximize and minimize buttons
  * Show/Hide close button
  * Double-clickable title bar
  * Enhanced title bar options
  * Configurable icons
  * Custom events



## Demo ##
  * Test Tool : http://jsbin.com/ehagoy/1/
  * _Stylesheet of JSBin seems to ruin test tool in IE8. Other browsers are fine._



## Tested Browsers ##
  * Chrome 20
  * Firefox 14
  * IE 8



## Options ##

  * **close** _<sup>(new in v1.0.1)</sup>_
    * Type: _Boolean_
    * Default: _true_
  * **maximize**
    * Type: _Boolean_
    * Default: _false_
  * **minimize**
    * Type: _Boolean_
    * Default: _false_
  * **dblclick**
    * Type: _Boolean, String_
    * Default: _false_
    * Valid: _false, 'maximize', 'minimize', 'collapse'_
  * **titlebar**
    * Type: _Boolean, String_
    * Default: _false_
    * Valid: _false, 'none', 'transparent'_
  * **icons**
    * Type: _Object_
    * Default:
```
{
  "close" : "ui-icon-circle-closethick", // new in v1.0.1
  "maximize" : "ui-icon-extlink",
  "minimize" : "ui-icon-minus",
  "restore" : "ui-icon-newwin"
}
```
    * Valid: _<jQuery UI icon class>_
  * **events**
    * Type: _Object_
    * Valid: _<Refer to **Events** section below>_



## Events ##

  * **load**
    * Type: _load.dialogExtend_
    * Example:
```
//Specify callback as init option
$("#my-dialog").dialogExtend({
  "events" : { "load" : function(evt, dlg) { ... } }
});
//Bind to event by type
//NOTE : You must bind() the <load.dialogExtend> event before dialog-extend is created
$("#my-dialog")
  .bind("load.dialogExtend", function(evt, dlg) { ... })
  .dialogExtend();
```
  * **beforeCollapse**
    * Type: _beforeCollapse.dialogExtend_
    * Example:
```
//Specify callback as init option
$("#my-dialog").dialogExtend({
  "events" : { "beforeCollapse" : function(evt, dlg) { ... } }
});
//Bind to event by type
$("#my-dialog").bind("beforeCollapse.dialogExtend", function(evt, dlg) { ... });
```
  * **beforeMaximize**
    * Type: _beforeMaximize.dialogExtend_
    * Example:
```
//Specify callback as init option
$("#my-dialog").dialogExtend({
  "events" : { "beforeMaximize" : function(evt, dlg) { ... } }
});
//Bind to event by type
$("#my-dialog").bind("beforeMaximize.dialogExtend", function(evt, dlg) { ... });
```
  * **beforeMinimize**
    * Type: _beforeMinimize.dialogExtend_
    * Example:
```
//Specify callback as init option
$("#my-dialog").dialogExtend({
  "events" : { "beforeMinimize" : function(evt, dlg) { ... } }
});
//Bind to event by type
$("#my-dialog").bind("beforeMinimize.dialogExtend", function(evt, dlg) { ... });
```
  * **beforeRestore**
    * Type: _beforeRestore.dialogExtend_
    * Example:
```
//Specify callback as init option
$("#my-dialog").dialogExtend({
  "events" : { "beforeRestore" : function(evt, dlg) { ... } }
});
//Bind to event by type
$("#my-dialog").bind("beforeRestore.dialogExtend", function(evt, dlg) { ... });
```
  * **collapse**
    * Type: _collapse.dialogExtend_
    * Example:
```
//Specify callback as init option
$("#my-dialog").dialogExtend({
  "events" : { "collapse" : function(evt, dlg) { ... } }
});
//Bind to event by type
$("#my-dialog").bind("collapse.dialogExtend", function(evt, dlg) { ... });
```
  * **maximize**
    * Type: _maximize.dialogExtend_
    * Example:
```
//Specify callback as init option
$("#my-dialog").dialogExtend({
  "events" : { "maximize" : function(evt, dlg) { ... } }
});
//Bind to event by type
$("#my-dialog").bind("maximize.dialogExtend", function(evt, dlg) { ... });
```
  * **minimize**
    * Type: _minimize.dialogExtend_
    * Example:
```
//Specify callback as init option
$("#my-dialog").dialogExtend({
  "events" : { "minimize" : function(evt, dlg) { ... } }
});
//Bind to event by type
$("#my-dialog").bind("minimize.dialogExtend", function(evt, dlg) { ... });
```
  * **restore**
    * Type: _restore.dialogExtend_
    * Example:
```
//Specify callback as init option
$("#my-dialog").dialogExtend({
  "events" : { "restore" : function(evt, dlg) { ... } }
});
//Bind to event by type
$("#my-dialog").bind("restore.dialogExtend", function(evt, dlg) { ... });
```



## Methods ##

  * **collapse**
    * Usage: Collapse the dialog without double-clicking the title bar
    * Trigger: _beforeCollapse.dialogExtend, collapse.dialogExtend_
    * Example:
```
$("#my-dialog").dialogExtend("collapse");
```

  * **maximize**
    * Usage: Maximize the dialog without clicking the button
    * Trigger: _beforeMaximize.dialogExtend, maximize.dialogExtend_
    * Example:
```
$("#my-dialog").dialogExtend("maximize");
```

  * **minimize**
    * Usage: Minimize the dialog without clicking the button
    * Trigger: _beforeMinimize.dialogExtend, minimize.dialogExtend_
    * Example:
```
$("#my-dialog").dialogExtend("minimize");
```

  * **restore**
    * Usage: Restore the dialog from maximized/minimized/collapsed state without clicking the button
    * Trigger: _beforeRestore.dialogExtend, restore.dialogExtend_
    * Example:
```
$("#my-dialog").dialogExtend("restore");
```

  * **state** _<sup>(new in v1.0.1)</sup>_
    * Usage: Get current state of dialog
    * Return: String
    * Value: _'normal', 'maximized', 'minimized', 'collapsed'_
    * Example:
```
switch ( $("#my-dialog").dialogExtend("state") ) {
  case "maximized":
    alert("The dialog is maximized");
    break;
  case "minimized":
    alert("The dialog is minimized");
    break;
  case "collapsed":
    alert("The dialog is collapsed");
    break;
  default:
    alert("The dialog is normal");
}
```



## Theming ##

The dialog will have class according to its current state.
```
<div class="ui-dialog">
  <div class="ui-dialog-titlebar">...</div>
  <div class="ui-dialog-content ui-dialog-{normal|maximized|minimized|collapsed}">...</div>
</div>
```

The buttons are wrapped by title bar of jQuery UI Dialog.

_Note : After using dialogExtend, close button will not be a direct child of title bar anymore. It will be wrapped by a button pane element_
```
<div class="ui-dialog-titlebar ui-widget-header ui-corner-all ui-helper-clearfix">
  ...
  <div class="ui-dialog-titlebar-buttonpane">
    <a class="ui-dialog-titlebar-close ui-corner-all" href="#">...</a>
    <a class="ui-dialog-titlebar-maximize ui-corner-all" href="#"><span class="ui-icon {icons.maximize}">maximize</span></a>
    <a class="ui-dialog-titlebar-minimize ui-corner-all" href="#"><span class="ui-icon {icons.minimize}">minimize</span></a>
    <a class="ui-dialog-titlebar-restore ui-corner-all" href="#"><span class="ui-icon {icons.restore}">restore</span></a>
  </div>
  ...
</div>
```



## Example - Basic Config ##
```
$(function(){
  $("#my-button").click(function(){
    $("<div>This is content</div>")
      .dialog({ "title" : "My Dialog" })
      .dialogExtend({
        "maximize" : true,
        "dblclick" : "maximize",
        "icons" : { "maximize" : "ui-icon-arrow-4-diag" }
      });
  });
});​
```



## Example - Full Config ##
```
$(function(){
  $("#my-button").click(function(){
    $("<div>This is  content</div>")
      .dialog({
        "title" : "This is dialog title",
        "buttons" : { "OK" : function(){ $(this).dialog("close"); } }
       })
      .dialogExtend({
        "close" : true,
        "maximize" : true,
        "minimize" : true,
        "dblclick" : "collapse",
        "titlebar" : "transparent",
        "icons" : {
          "close" : "ui-icon-circle-close",
          "maximize" : "ui-icon-circle-plus",
          "minimize" : "ui-icon-circle-minus",
          "restore" : "ui-icon-bullet"
        },
        "events" : {
          "load" : function(evt, dlg){ alert(evt.type+"."+evt.handleObj.namespace); },
          "beforeCollapse" : function(evt, dlg){ alert(evt.type+"."+evt.handleObj.namespace); },
          "beforeMaximize" : function(evt, dlg){ alert(evt.type+"."+evt.handleObj.namespace); },
          "beforeMinimize" : function(evt, dlg){ alert(evt.type+"."+evt.handleObj.namespace); },
          "beforeRestore" : function(evt, dlg){ alert(evt.type+"."+evt.handleObj.namespace); },
          "collapse" : function(evt, dlg){ alert(evt.type+"."+evt.handleObj.namespace); },
          "maximize" : function(evt, dlg){ alert(evt.type+"."+evt.handleObj.namespace); },
          "minimize" : function(evt, dlg){ alert(evt.type+"."+evt.handleObj.namespace); },
          "restore" : function(evt, dlg){ alert(evt.type+"."+evt.handleObj.namespace); }
        }
      });
  });
});​
```