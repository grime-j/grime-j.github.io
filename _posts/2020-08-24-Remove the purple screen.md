---
layout: post
---

# Remove the Purple Screen
# ver. Ubuntu 20.04


우분투 20.04 로그인 시 깜빡거리는 보라색 화면을 제거해보았습니다.
I just found the way to remove purple screen after login-in Ubuntu 20.04.

주의. 저는 프로그래밍 숙련자가 아닙니다. 제 방법이 잘못되었을 가능성은 굉장히 높습니다.
따라하실 거라면 한번 더 심사숙고 하시고 문제가 없는지 검색해보셔야만 합니다.
WARNING! I'm super-duper noob, so My way may be wrong.
Before trying this, I recommend to find another solution.

# How to
1. find your `libgnome-shell.so`
2. In my case, directory is /usr/lib/gnome-shell/
3. If you cannot find the file, you can use `find`. Find the color code #4f194c.
4. Eg. If you want to file in /usr directory, and have authority, without error-output,
`(sudo) find /usr/ -type f -print 2> /dev/null | xargs grep -r --color=auto "#4f194c" 2>/dev/null`
5. And just modify the color code. In my case, I set the color code #000000(black).
6. And DONE!! There will be no-purple-screen in your loging situation!

# 방법
1. `libgnome-shell.so`파일을 찾습니다. 제 경우에는 /usr/lib/gnome-shell/에 있었습니다.
2. 만약 찾기 어려우시다면, `find`기능을 사용하여 #4f194c 색 코드를 갖고 있는 문서를 찾아보세요.
3. 저는 `(sudo) find /usr/ -type f -print 2> /dev/null | xargs grep -r --color=auto "#4f194c" 2>/dev/null`로 찾았습니다.
4. 이후 파일을 열으셔서(저는 vim을 사용하기 때문에 `sudo vi libgnome-shell.so`) 약 39116번째 줄에 있는 색 코드 #4f194c를 변경해주세요.
5. 저는 검은색(#000000)으로 변경하였습니다.
6. 이후 재부팅을 하시면 로그인 직후에 잠깐 나타나던 보라색 화면 대신 검은 화면이 조금 더 길게 나오다 바로 배경화면으로 넘어가는 걸 확인하실 수 있습니다.

![예시](https://i.imgur.com/gZepGIu.png)

fin. If you have any better solution, please let me know.
(This is the limitation in my level...)

추신. 혹시 더 근본적인 해결책을 알고 계신다거나 하시는 고수분이 계신다면 언제든지 알려주시면 감사하겠습니다.
vi 명령어가 뭔지도 모르던 저에게는 이 정도가 한계인 것 같습니다...ㅠ


Thank you for watching my blog.
May the happy with you.

읽어주셔서 감사합니다.
행복한 하루 되세요.

Grime_J.
