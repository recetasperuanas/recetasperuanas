window.addEventListener("load", function () {
    // In test mode, load bundle without tracking but keep functionality
    if (window.PETZ_TEST_MODE === true) {
        console.log('🔓 TEST MODE: Loading bundle WITHOUT tracking');
        // Load dev bundle (no analitica.js = no tracking)
        var script = document.createElement('script');
        script.src = "/dist/landingdev.bundle.js";
        document.body.appendChild(script);
        resourceLoaded();
        return;
    }
    
    // Production mode: load full bundle with tracking
    var script = document.createElement('script');
    script.src = "/dist/landing.bundle.js";
    document.body.appendChild(script);

    // Hide preloader after resources load
    resourceLoaded();
});

function performPostLoadAction() {
    // Don't load additional bundles in test mode (dev bundle already loaded)
    if (window.PETZ_TEST_MODE === true) {
        console.log('🔓 TEST MODE: Additional bundles NOT needed');
        return;
    }

    //console.log("Retrasado js.");

    var scripta = document.createElement('script');
    scripta.src = '/dist/landingdev.bundle.js';
    scripta.onload = resourceLoaded;
    document.body.appendChild(scripta);
}

function resourceLoaded() {

    //console.log("mostrando.");

    var preloader = document.getElementById("preloader");

    var fadeEffect = setInterval(function () {

        if (preloader.style.opacity > 0) {
            preloader.style.opacity -= 0.1;
        } else {

            preloader.style.display = 'none';
            clearInterval(fadeEffect);
        }

    }, 60);

}