<script src="https://unpkg.com/launchdarkly-js-client-sdk@2.18.1/dist/ldclient.min.js"></script>
<h1>Great LinkedIn Learning Courses</h1>
<h3> Embeding new content</h3>

<p> This is some useful description to practice git flow</p>
<p> This is some other content below first content</p>
<div id="preview" style="display:none"><p>PRacticing feature flagsss</p></div>
<script>
    var clientId = "6ac36bd223afbb0749c77e90";
    var flagName = "course-preview";
    var user = {anonymous: true};
    var ldclient = window.LDClient.initialize(clientId, user);

    ldclient.on("ready", function() {
        document.getElementById('preview').style.display = ldclient.variation(flagName,false)
        ? "block" : "none";
    })

    ldclient.on("change:" + flagName, function(newVal, prevVal) {
        document.getElementById("preview").style.display = newVal ? "block" : "none";
    } )

</script>
<p>Added new paragraph</p>
