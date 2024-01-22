---
layout: default
title: SOP Bypass - Testcase 3
permalink: /sop/new/3
---

# SOP Bypass - Testcase 3

<input type="button" id="btn_test" class="test" value="Run Test Case" onclick="sop()">
<script>
function sop() {
    var document;
    document = {};
    document.domain = 'bing.com';
    alert(document.location);
}
</script>

**Note:**
If page displays an alert box displaying bing.com, your browser is vulnerable to SOP bypass.
