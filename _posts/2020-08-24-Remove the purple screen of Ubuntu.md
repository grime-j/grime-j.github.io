---
layout: post
comments: true
---

<br/>

<div style="text-align: center">
   <div style= "font-size: 40px"><b>Remove <span style="color:purple">the Purple Screen</span></b></div>
   <div style="font-size: 25px"> in login situation of Ubuntu <i>ver. 20.04</i> </div></div>
<div style = "font-size: 14px">
<div style="text-align: right"><i>Posted by <b>Grime J.</b></i> on <i><b>Aug. 24, 2020</b></i></div> 
<div style="text-align: right"><span style="color:purple">Env: Ubuntu <i>ver. <b>20.04.1</b></i> LTS & Gnome shell <i>ver. <b>3.36.4</b></i></span></div></div> 
<br/>
<br/>
<br/>
<b>우분투 20.04 로그인 직후 바탕화면이 나오기 전에 잠깐 나오는 보라색 화면을 제거해보았습니다.</b>
- <span style="color:red"><b>주의!!</b></span> 저는 프로그래밍 초보입니다. 이 방법으로 문제가 생길 가능성은 많습니다.
- 따라하시기 전에 한번 더 심사숙고 하시고 문제가 없는지 검색해보셔야만 합니다.
- <span style="color:purple"> <b>요약</b></span>: <b>`libgnome-shell.so`</b> 파일을 찾아 <span style='color:purple'><b>`#4f194c`</b></span> 색 코드를 변경하시면 됩니다.


<b>I just found the way to remove purple screen after login-ing Ubuntu 20.04.</b>
- <span style="color:red"><b>WARNING!!</b></span> I am very very newbie, so my solution may be wrong.
- Before trying this, I recommend you to find another solution. Maybe there is some better one!
- <span style="color:purple"> <b>Summary</b></span>: Find the <b>`libgnome-shell.so`</b> file, and change the color code <span style='color:purple'><b>`#4f194c`</b></span>.

<br/>

## <b>방법</b>
1. `libgnome-shell.so`파일을 찾습니다. 제 경우에는 `/usr/lib/gnome-shell/`에 있었습니다.
2. 만약 찾기 어려우시다면, `find`기능을 사용하여 `#4f194c` 색 코드를 갖고 있는 문서를 찾아보세요.
3. 예시: 현재 위치를 포함하는 모든 하위 디렉토리에서 찾으려 할 경우
- `sudo find . -type f -print 2> /dev/null | xargs grep -r --color=auto -n "#4f194c" 2>/dev/null`
4. 파일을 여신 후에 약 `39116`번째 줄에 있는 `#4f194c` 색 코드를 변경해주세요. 저는 <b>검은색</b>(`#000000`)으로 하였습니다.
5. 이후 재부팅을 하시면 로그인 직후에 잠깐 나타나던 보라색 화면이 나오지 않는 걸 확인하실 수 있습니다!


## <b>Solution</b>
1. find your `libgnome-shell.so` file. In my case, That is in `/usr/lib/gnome-shell/`
2. If you cannot find the file, you can use `find`. Find the color code `#4f194c`.
3. Eg. Find all files, including your subdirectory on your current position.
- `sudo find . -type f -print 2> /dev/null | xargs grep -r --color=auto -n "#4f194c" 2>/dev/null`
4. And just modify the color code in about `39116`th row. In my case, I set the color code <b>black</b>(`#000000`).
5. And DONE!! There will be no-purple-screen in your login-ing situation!

<br/>

![예시](https://i.imgur.com/gZepGIu.png)

<br/>

### <i><span style="color:green"><b>부록</b></span>. 계기와 시행착오에 대하여 / <span style="color:green"><b>Appendix</b></span>. How can I do this?</i>
- <span style="color:green"> 다음 주 주중 안</span>에 업데이트하도록 하겠습니다.
- I'll update in <span style="color:green"> next week.</span>

<br/>

<b><i>마치며</i></b>.
<br/>
혹시 더 멋지거나 깔끔한 방법을 알고 계신 분은 언제든지 알려주시면 감사하겠습니다!
<br/>
읽어주셔서 감사합니다. 행복한 하루 되세요.


<b><i>fin</i></b>. 
<br/>
If you have any better solution, please let me know. (~~This is the limitation in my level...~~)
<br/>
Thank you for watching my post. May the happiness be with you.

<br/>

### <i>Grime J.</i>

<br/>

{% if page.comments %}
<div id="post-disqus" class="container">
{% include custom_comments_provider.html %}
</div>
{% endif %}
