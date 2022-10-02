---
backlinks:
  - G915 TKLとMagic Keyboardの二刀流を検討する
  - Windows PCでMac風キーバインドを目指す（G915 TKL編）
date: 2022-10-02 23:06:02 +0900
published: true
---

# easy-input-switch-ahk

- [[AutoHotKey]]のスクリプト
	- RCtrl単体押しで無変換キーを送信
	- LAlt単体押しで無変換キーを送信
	- RAlt単体押しで変換キーを送信

```ahk
; ref:
; - https://github.com/karakaram/alt-ime-ahk/blob/master/alt-ime-ahk.ahk
; - https://github.com/nekocodeX/alt-ime-ahk-mod/blob/main/alt-ime-ahk-mod.ahk

; 主要なキーをHotKeyに設定し、何もせずパススルーする
*~a::
*~b::
*~c::
*~d::
*~e::
*~f::
*~g::
*~h::
*~i::
*~j::
*~k::
*~l::
*~m::
*~n::
*~o::
*~p::
*~q::
*~r::
*~s::
*~t::
*~u::
*~v::
*~w::
*~x::
*~y::
*~z::
*~1::
*~2::
*~3::
*~4::
*~5::
*~6::
*~7::
*~8::
*~9::
*~0::
*~F1::
*~F2::
*~F3::
*~F4::
*~F5::
*~F6::
*~F7::
*~F8::
*~F9::
*~F10::
*~F11::
*~F12::
*~`::
*~~::
*~!::
*~@::
*~#::
*~$::
*~%::
*~^::
*~&::
*~*::
*~(::
*~)::
*~-::
*~_::
*~=::
*~+::
*~[::
*~{::
*~]::
*~}::
*~\::
*~|::
*~;::
*~'::
*~"::
*~,::
*~<::
*~.::
*~>::
*~/::
*~?::
*~Esc::
*~Tab::
*~Space::
*~Left::
*~Right::
*~Up::
*~Down::
*~Enter::
*~PrintScreen::
*~ScrollLock::
*~Pause::
*~Insert::
*~Delete::
*~Home::
*~End::
*~PgUp::
*~PgDn::
  Return

; 下で使うためにHotKeyを設定しておく
*~RCtrl::Return

; 右Ctrl空打ちで無変換を送信
RCtrl Up::
  if (A_PriorHotkey == "*~RCtrl")
  {
    Send, {vk1D}
  }
  Return

; 上部メニューがアクティブになるのを抑制
*~LAlt::Send {Blind}{vkFF}
*~RAlt::Send {Blind}{vkFF}

; 左Alt空打ちで無変換を送信
LAlt Up::
  if (A_PriorHotkey == "*~LAlt")
  {
    Send, {vk1D}
  }
  Return

; 右Alt空打ちで変換を送信
RAlt Up::
  if (A_PriorHotkey == "*~RAlt")
  {
    Send, {vk1C}
  }
  Return

```
