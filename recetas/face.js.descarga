// Facebook Pixel and Conversions API Synchronization
(function() {
    'use strict';
    
    // Function to set a cookie
    function setCookie(name, value, days) {
        var expires = "";
        if (days) {
            var date = new Date();
            date.setTime(date.getTime() + (days * 24 * 60 * 60 * 1000));
            expires = "; expires=" + date.toUTCString();
        }
        document.cookie = name + "=" + (value || "") + expires + "; path=/; SameSite=Strict";
    }
    
    // Function to get a cookie
    function getCookie(name) {
        var nameEQ = name + "=";
        var ca = document.cookie.split(';');
        for(var i = 0; i < ca.length; i++) {
            var c = ca[i];
            while (c.charAt(0) == ' ') c = c.substring(1, c.length);
            if (c.indexOf(nameEQ) == 0) return c.substring(nameEQ.length, c.length);
        }
        return null;
    }
    
    // Generate unique session ID if it doesn't exist
    var sessionId = getCookie('fb_session_id');
    if (!sessionId) {
        sessionId = 'sess_' + Date.now() + '_' + Math.random().toString(36).substr(2, 9);
        setCookie('fb_session_id', sessionId, 1); // Expires in 1 day
    }
    
    // Store page view event ID for server-side API
    var pageViewEventId = 'PetzSite_' + Date.now() + '_' + Math.floor(Math.random() * 9000 + 1000);
    setCookie('fb_pageview_event_id', pageViewEventId, 1);
    
    // Store page title for server-side API
    setCookie('fb_page_title', document.title, 1);
    
    // Enhanced Facebook Pixel initialization
    !function(f,b,e,v,n,t,s) {
        if(f.fbq) return;
        n = f.fbq = function() {
            n.callMethod ? n.callMethod.apply(n,arguments) : n.queue.push(arguments)
        };
        if(!f._fbq) f._fbq = n;
        n.push = n;
        n.loaded = !0;
        n.version = '2.0';
        n.queue = [];
        t = b.createElement(e);
        t.async = !0;
        t.src = v;
        s = b.getElementsByTagName(e)[0];
        s.parentNode.insertBefore(t,s)
    }(window, document, 'script', 'https://connect.facebook.net/en_US/fbevents.js');
    
         // Initialize Facebook pixels
     fbq('init', '700996330520730');  // MAIN Petz School
fbq('init', '2832144410330423');
fbq('init', '372361850883221');
fbq('init', '3067315600166617');

    // Track PageView with synchronized event ID
    fbq('track', 'PageView', {
        eventID: pageViewEventId,
        content_type: 'website',
        page_title: document.title
    });
    

    
})(); 