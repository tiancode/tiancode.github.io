---
layout: post
title: JavaScript键码值
---

按下你要查询的健，返回键码。

<input type="text" maxlength="0" size="2">

<script>
  window.addEventListener("keydown", function (event) {
    document.getElementById("code").innerHTML = event.keyCode;
    if (event.key) {
      if (event.keyCode > 47 && event.keyCode < 91) {
        document.getElementById("char").innerHTML = " - " + String.toUpperCase(event.key);
      } else {
        document.getElementById("char").innerHTML = " - " + event.key;
      }
    }
  }, false);
</script>
<span id="code" style="background-color: #faee95; font-size: 100;  border-style: solid; border-width: 5px; border-color: #848789"></span>
<span id="char" style="font-size: 70;"></span>