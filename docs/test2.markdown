---
layout: default
title: SOP Bypass - Testcase 2
permalink: /sop/new/2
---

<input type="button" id="btn_test" class="test" value="Run Test Case" onclick="myfunc()">
<script>
function myfunc() {
    alert(frames[0].location)
}
</script>

**Note:**
If page displays an alert box displaying bing.com, your browser is vulnerable to SOP bypass.
