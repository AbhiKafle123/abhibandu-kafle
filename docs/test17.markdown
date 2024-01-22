---
layout: default
title: SOP Bypass - Testcase 17
permalink: /sop/new/17
---

# SOP Bypass - Testcase 17

Based upon Mario Heiderich's IE UXSS

<script>
function myfunction() {
    x = document.createElement("IFRAME");
    x.setAttribute("width", "0");
    x.setAttribute("height", "0");
    x.setAttribute("src", "https://web.archive.org/web/20180831134345/http://innerht.ml/refresh.html");
    document.body.appendChild(x);
}
</script>

<input type="button" id="btn_test" class="test" value="Run Test Case" onclick="myfunction()">

**Note:**
If page displays an alert box displaying innerht.ml, your browser is vulnerable to SOP bypass.
