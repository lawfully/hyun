---
title: 가변폰트
categories: [personal,fonts,tech]
---

`texdoc` 명령을 쓰면, 매뉴얼을 읽을 수 있다. 가변폰트(라 해야 하나? variable font) 사용법을 제대로 익혀 보기로 했다. 그래서 [해피니스 산스](https://thehyundaifont.com/?source=post_page-----ad1a2fdff11c---------------------------------------), 현대백화점에서 만든 폰트라 한다, 이걸 가지고 해 보기로 했다. 다운로드받아 압축을 풀고, `texdoc fontspe`으로 `fontspec` 매뉴얼을 일기 시작한다.

```bash
$ otfinfo -i Happiness-Sans-Print-Regular.otf
Family:              Happiness Sans Print Regular
Subfamily:           Regular
Full name:           Happiness Sans Print Regular
PostScript name:     Happiness-Sans-Print-Regular
Preferred family:    Happiness Sans Print
Preferred subfamily: Regular
Version:             Version 1.000; Build 20220220
```

$$\LaTeX$$에서는

```latex
\defaultfontfeatures{RawFeature={+axis={wght=300}},Ligatures=TeX}
\setkosansfont[HappinessSansPrint](Regular)
```

이렇게 하면 되는데, 여기에 *+axis*를 조절해서 여러가지를 해볼 수 있다는 것 같은데,