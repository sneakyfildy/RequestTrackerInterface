# RequestTrackerInterface
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