# Demo: Disabled

<span class="context-menu-one label label-default">right click me</span>

## Example code

<script type="text/javascript" class="showcase">
$(function(){
    $.contextMenu({
        selector: '.context-menu-one', 
        callback: function(key, options) {
            var m = "clicked: " + key;
            window.console && console.log(m) || alert(m); 
        },
        items: {
            "edit": {name: "Edit", icon: "edit"},
            "cut": {name: "Cut", icon: "cut"},
            "copy": {name: "Copy", icon: "copy"},
            "paste": {name: "Paste", icon: "paste"},
            "delete": {name: "Delete", icon: "delete"},
            "sep1": "---------",
            "quit": {name: "Quit", icon: function($element, key, item){ return 'icon icon-quit'; }}
        }
    });
    
    $('#toggle-disabled').on('click', function(e) {
        e.preventDefault();
        var $this = $(this),
            $trigger = $('.context-menu-one');
        if ($trigger.hasClass('context-menu-disabled')) {
            $this.text("Disable Menu");
            $trigger.contextMenu(true);
        } else {
            $this.text("Enable Menu");
            $trigger.contextMenu(false);
        }
    });
});
</script>

## Example HTML
<div style="display:none;" class="showcase" data-showcase-import=".context-menu-one"></div>