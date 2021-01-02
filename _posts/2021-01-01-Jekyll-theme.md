---
layout: post
title:  jekyll theme를 사용한 기술 블로그 만들기
date:   "2021-01-001 15:50:15"
author: Anderson
categories: Code
tag: groovy
cover:  "/assets/instacode.png"
---

출처 : https://hoik92.github.io/jekyll/2019/05/29/Make-blog-using-jekyll.html


### 1) Ruby 설치하기  

  > [Ruby+devkit 2.7.2-1(x64)](https://rubyinstaller.org/downloads/)


### 2) Start Command Prompt with Ruby 실행


### 3) gem package를 사용하여 Jekyll 설치 : 로컬에서 블로그 구성이 가능해진다  

  * 명령어 
    - gem install jekyll
  
    - gem install minima  
  
    - gem install jekyll-feed  
  
    - gem install tzinfo-data


### 4) 로컬에 블로그를 관리할 폴더를 생성하고 해당 경로로 이동한다  


### 5) Jekyll 실행

  * 명령어
    - jekyll serve
    - chop 65001 /* 인코딩 에러 발생 시 */


### 6) 웹브라우져를 열고 127.0.0.1:4000 으로 이동하면 로컬 블로그가 생성된 것을 확인 할수 있다  


### 7) Github에서 원하는 jekyll 테마를 찾는다  


### 8) Clone or download --> Download ZIP   


### 9) _config.yml을 열고 base url과 url을 수정한다 (url : https://DevPageAnderson.github.io)  


### 10) Gemfile.lock 파일을 삭제한다  


### 11) command창에서 경로를 jekyll 테마를 저장한 경로로 변경하고 명령어 수행  

  * 명령어
    - bundle install

    - jekyll serve


### 12) 127.0.0.1:4000를 새로고침하면 해당 테마가 로컬블로그에 반영된다  


### 13) Github에서 새로운 저장소를 생성한다  
  - <Github 사용자 이름>.github.io

  - _config.yml 파일의 url과 동일해야 한다


### 14) Remote 실행  
  * 명령어
    - git init

    - git add .

    - git commit -m "<커밋 메세지>"

    - git remote add origin https://github.com/DevPageAnderson/DevPageAnderson.github.io.git

    - git push -u origin master


### 15) 조금 기다린 후 https://DevPageAnderson.github.io 접속  

