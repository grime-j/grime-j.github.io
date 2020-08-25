---
layout: post
---

### **Remove the Purple Screen in login-ing situation**
##### <span style="color:purple">ENV: *Ubuntu ver. **20.04.1 LTS** & Gnome Shell ver. **3.36.4***
##### *Posted by **Grime J**. on **Aug. 24, 2020. (UTC+9)** / **2020-08-24***

<br/>


**우분투 20.04 로그인 직후에 잠깐 나타나던 보라색 화면을 제거해보았습니다.**
- <span style="color:red">**주의!!**</span> 저는 프로그래밍 초보입니다. 이 방법으로 문제가 생길 가능성은 많습니다.
- 따라하시기 전에 한번 더 심사숙고 하시고 문제가 없는지 검색해보셔야만 합니다.
- <span style="color:purple"> **요약**</span>: **`libgnome-shell.so`** 파일을 찾아 **`#4f194c`** 색 코드를 변경하시면 됩니다.


**I just found the way to remove purple screen after login-ing Ubuntu.**
- <span style="color:red">**WARNING!!**</span> I am very very newbie, so my solution may be wrong.
- Before trying this, I recommend you to find another solution. Maybe there is some better one!
- <span style="color:purple"> **Summary**</span>: Find the **`libgnome-shell.so`** file, and change the color code **`#4f194c`.**

<br/>

## **방법**
1. `libgnome-shell.so`파일을 찾습니다. 제 경우에는 `/usr/lib/gnome-shell/`에 있었습니다.
2. 만약 찾기 어려우시다면, `find`기능을 사용하여 `#4f194c` 색 코드를 갖고 있는 문서를 찾아보세요.
3. 예시: 현재 위치를 포함하는 모든 하위 디렉토리에서 찾으려 할 경우
- `sudo find . -type f -print 2> /dev/null | xargs grep -r --color=auto -n "#4f194c" 2>/dev/null`
4. 파일을 여신 후에 약 `39116`번째 줄에 있는 `#4f194c` 색 코드를 변경해주세요. 저는 **검은색**(`#000000`)으로 하였습니다.
5. 이후 재부팅을 하시면 로그인 직후에 잠깐 나타나던 보라색 화면이 나오지 않는 걸 확인하실 수 있습니다!

<br/>

## **Solution**
1. find your `libgnome-shell.so` file. In my case, That is in `/usr/lib/gnome-shell/`
2. If you cannot find the file, you can use `find`. Find the color code `#4f194c`.
3. Eg. Find all files, including your subdirectory on your current position.
- `sudo find . -type f -print 2> /dev/null | xargs grep -r --color=auto -n "#4f194c" 2>/dev/null`
4. And just modify the color code in about `39116`th row. In my case, I set the color code **black**(`#000000`).
5. And DONE!! There will be no-purple-screen in your login-ing situation!

<br/>

![예시](https://i.imgur.com/gZepGIu.png)

<br/>


### *참조. 알아낸 방법 / Appendix. How I find this solution?*
- <span style="color:green"> 다음 주 주중 안</span>에 업데이트하도록 하겠습니다.
- I'll update in <span style="color:green"> next week.</span>

<br/>
<br/>

**_마치며_**. 혹시 더 멋지거나 깔끔한 방법을 알고 계신 언제든지 알려주세요!

읽어주셔서 감사합니다. 행복한 하루 되세요.

**_fin_**. If you have any better solution, please let me know. (This is the limitation in my level...)

Thank you for watching my blog. May the happiness with you.

### *Grime J.*

