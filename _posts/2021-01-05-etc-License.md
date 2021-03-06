---
layout: post
title:  License
date:   "2021-01-05 21:54:15"
author: Anderson
categories: Code
tag: Etc
cover:  "/assets/instacode.png"
---

# 오픈소스에 대한 License

본 내용은 개인적인 조사 결과이며, 법적 검토 시 참고 할수 없습니다.

License란 해당 소스코드의 제작자와 사용자 건의 유상 또는
무상의 계약을 의미하며 오픈소스에 대한 제작자의 책임 및 유지보수 등의 의무가 없음을 밝히는 의미가 있다
대부분의 오픈소스에는 License가 존재하며, 상업용 License는 
각 제작사마다 상이하다

## 오픈소스 관련 License

1) License가 없는 경우
    - License가 명시되지 않은 경우 제작자가 모든 권한을 100%소유하므로 임의로 해당 소스를 사용해선 안된다
2) GPL
    _ 본인이 개발한 코드를 공개하지 않으려면 사용하지 마라
    - 상업적 판매 또는 배포 시 본인이 개발/수정한 코드를 공개해야 하며, 해당 GPL Licese의 출처를 함께 공개한다
    
3) LGPL
    - GPL을 완화한 것
    - 경우1) LGPL license 관련 코드와 본인이 개발한 코드가 바이너리파일(.exe)로 컴파일 되어 판매되거나 배포되는 경우는 GPL과 동일하다
    - 경우2) LGPL license 관련 코드(라이브러리)를 별도 dll로 지정하여 동적으로 연결하여 사용하고 본인이 개발한 코드는 독자적으로 실행되는 경우는 소스코드 공개의 의무가 없다 (LGPL license 관련 코드를 수정하지 않는 조건)
4) AGPL
    - 과거에 웹서버에서 실행되는 것은 배포 또는 판매로 보지 않는 사례가 있었고, 이러한 점을 악이용하지 않기 위해 등장함
    - 웹서버에서 실행되는 AGPL license 관련 코드를 활용하여 개발된 소스코드는 공개되어야 한다
5) MIT, Aphche, BSD
    - 해당 소스코드에 대한 사용 여부만을 알리면 된다
    - 상용 판매 또는 배포 시 제약이 없고 마음껏 수정이 가능하다
    - 최신 트렌드에 부합하는 진정한 오픈소스의 개념이다