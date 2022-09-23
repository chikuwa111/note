---
backlinks:
  - Windows PCでMac風キーバインドを目指す（G915 TKL編）
date: 2022-09-07 17:36:16 +0900
published: true
---

# emacs-like-key-bindings-ahk

- [[AutoHotKey]]のスクリプト
	- [[Mac OS]]で見られる[[Emacs]]風のキーバインドを設定する

```ahk
LCtrl & a::send_custom_command("{Home}")
LCtrl & b::send_custom_command("{Left}")
LCtrl & d::send_custom_command("{Delete}")
LCtrl & e::send_custom_command("{End}")
LCtrl & f::send_custom_command("{Right}")
LCtrl & h::send_custom_command("{Backspace}")
LCtrl & k::send_custom_command("+{End}{Delete}")
LCtrl & n::send_custom_command("{Down}")
LCtrl & p::send_custom_command("{Up}")

; 修飾キーつきで別のコマンドをSendする
send_custom_command(command) {
  m := ""
  if (GetKeyState("LWin", "P") or GetKeyState("RWin", "P")) {
    m = %m%#
  }
  if GetKeyState("Shift", "P") {
    m = %m%+
  } 
  if GetKeyState("Alt", "P") {
    m = %m%!
  }
  Send, %m%%command%
}

```