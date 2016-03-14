# RequestTrackerInterface
Requires jQuery to do AJAX.
Implement RT.nonJqueryAjax method to avoid it.
Remember about CORS.
Was born to work inside chrome extension.

Usage:
var RT = new RTIConstructor({
    url: 'url.to.rt', // default to some RT demo
    debug: false // default true, because very-very raw and dev
});

RT.getTicket(1, onGetTicket);

function onGetTicket(res){
    if (!res.success){
        console.error(res.errorText);
    }else{
        doSomethingWith(res.ticketData);
    }
}

OR

define([
    'rt'
], function(RTIConstructor){
    RT = new RTIConstructor({
        url: 'url.to.rt'
    });
    RT.getTicket(1, onGetTicket);    
});