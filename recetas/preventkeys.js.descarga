jQuery( function() {

	jQuery( "body" ).on('keypress',function() {
		return disableCtrlKeyCombination(event);	
	})

	jQuery( "body" ).on('keydown',function() {
		return disableCtrlKeyCombination(event);	
	})
	
	jQuery( "body" ).on('mousedown ',function() {
		return disableCtrlKeyCombinationmd(event);	
	})	
	
	if (document.layers){
		document.captureEvents(Event.MOUSEDOWN);
		document.onmousedown=clickNS;
	}else{
		document.onmouseup=clickNS;
		document.oncontextmenu=clickIE;
	} 

	document.oncontextmenu=new Function("return false");
	
});

var forbiddenKeys = new Array('a', 'n', 'c', 'x', 'v', 'j' , 'w', 's', 'u');
var key;
var isCtrl;

function disableCtrlKeyCombinationmd(event){
	event = (event || window.event);
	
	if (event.keyCode == 123) {
		return false;
	}	
}

function disableCtrlKeyCombination(e){
	
	
	event = (event || window.event);
	if (event.keyCode == 123) {
		return false;
	}	
	

	if(window.event){
		key = window.event.keyCode; //IE
		if(window.event.ctrlKey)
			isCtrl = true;
		else
			isCtrl = false;
	}else{
		key = e.which; //firefox
		if(e.ctrlKey)
			isCtrl = true;
		else
			
			if (key == 123) {
				return false;
			}
			
			isCtrl = false;
	}
	
	//if ctrl is pressed check if other key is in forbidenKeys array
	if(isCtrl){
		for(i=0; i<forbiddenKeys.length; i++){
			//case-insensitive comparation
			if(forbiddenKeys[i].toLowerCase() == String.fromCharCode(key).toLowerCase()){
				//alert("Key combination CTRL + "+String.fromCharCode(key) +" has been disabled.");
			return false;
			}
		}
	}
	return true;
}

function clickIE() {
	if (document.all) {
		return false;
	}
} 

function clickNS(e) {
	if (document.layers||(document.getElementById&&!document.all)) { 
		if (e.which==2||e.which==3) {
			return false;
		}
	}
} 
