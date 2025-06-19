---
title: 프린터와 인공지능
categories: [general]
---

요즘은 시간이 남을 때면, 그저 인공지능을 생각하고, 여기에 대해서 글을 읽고 오디오북을 듣게 됩니다. 어떻게든 신경쓰고, 걱정하고, 계획해야 하는 미래가 바로 여기 있으니까요. 문득 집에 새로운 프린터가 생겼습니다. 인공지능에서 벗어나서 순수한 삽질 -- 끝내고 나면 별것 아닌, 가치도 없어 보이는 일을 할 기회죠. 게다가 아내님의 엄명이니... 문제는 `smb`를 설정하는 것이었습니다. 솔직히 집사람은 그런 것은 신경도 안쓰지만, 스캔을 했을 때 제가 쓰는 리눅스 컴퓨터의 삼바 폴더로 저장되길 원했던거죠. 우여곡절 끝에, 전체 시간은 훨씬 적겠지만, 시작에서 끝까지 24시간 이내에 해결했네요. 문제는 `smb` 이거 리눅스와는 별로 잘 안맞아서 여러가지 신경 쓸 일이 많았죠. 평소같으면 하지도 않을 일이었겠지만, ... 덤으로 아이폰 파일 앱에서 그 삼바 폴더로 바로 접속할 수 있도록 하기도 했습니다. 꽤나 오랜 시간이 걸렸지만, 결국 문제는 `netbios` 설정... 이라고 해야 하나...

~~~bash
[global]
   workgroup = WORKGROUP
   local master = yes
   preferred master = yes
   domain master = yes
   netbios name = ZENBOOK
   server string = Samba %v
   # NetBIOS
   wins support = yes
   local master = yes
   preferred master = yes
   os level = 65
~~~

결국 이 부분을 명시적으로 규정해 줘야 프린터에서 컴퓨터의 삼바를 찾더라구요. 그리고, 또 중요한, 꼭 해야 하는 변경 두 가지...

~~~bash
  usershare path = /srv/samba/public
  usershare max shares = 100
  usershare allow guests = yes
  usershare owner only = no
~~~

이건 꼭 필요한 이유가 `AppArmor` 설정을 제대로 하지 않으면, 홈 디렉토리가 아닌 곳에 파일을 읽고 쓰는데 문제가 생기기 때문이고,

~~~bash
  fruit:copyfile = yes
  fruit:nfs_aces = yes
  fruit:aapl = yes
  idmap config * : backend = tdb
  vfs objects = catia fruit streams_xattr
~~~

이건 아이폰 파일 앱에서 여기 접속하려면 꼭 필요하다고... 이유는 모르겠지만, 뭔가 아이폰 파일 앱에서 쓰는 프로그램 버전이 너무 낮아서일 거라고... 하여튼 이렇게 **과일** 설정을 해줘야 한다고...

하여튼 이 세 가지만 제대로 정리해 주고 나면, 나머지는 취향에 따라... 설정하면 됩니다.

--- 

이런 문제를 처음 접하는 것도 아니고, 시간이 들어도 결국 해결하고 나면 왠지 뿌듯해지는 그 짜릿한 느낌 때문에 나름 도전하기도 하지만, 
[Warp](https://www.warp.dev/)를 쓰고, [github copilot](https://github.com/features/copilot)를 이용해서 문제를 해결하는 과정은 그 과정 자체가 아주 다른 느낌을 준다. 뭐랄까, 과거에는 오류가 생기면 정황과 오류 메시지 등을 기준으로 나름 추리를 하고, 구글을 열심히 탐색하면서 답을 찾아 나가는 과정은 지금 생각해 보면 마치 깜깜한 밤 좁은 범위만 비춰 주는 랜턴을 가지고 산을 올라가는 느낌이었다면, AI를 이용한 문제 해결은 환한 대낮에 지도와 스마트폰으로 무장하고 전체를 다 보면서 산을 올라가는 것과 비슷한 느낌이랄까... 그렇다고 해서 딱히 시간이 적게 드는 것은 아니다. 왜냐하면, 결국 LLM은 나의 언어습관과 내 생각의 반영일 뿐이니까... 내가 추측하고 가정하는 어떤 상황에 대한 이해를 끝까지 밀어 붙이면 이렇게 될 것이라 생각하는 그 상황을 분명히 보여주는 이상도 이하도 아니다.