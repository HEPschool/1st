# README_Lecturer
README_Lecturer에서는 Lecturer, Lecture·Special talk event, Lecturer material 등록·관리 방법을 안내합니다. <br/><br/><br/>

## 주의 사항 <br/>
등록·관리 과정에서 입력한 값들은 홈페이지 및 repository에 표시됩니다. <br/>
입력된 값들은 홈페이지 및 repository 주소를 아는 모든 사용자들에 의해 열람/다운로드가 가능합니다. <br/>
민감한 정보/자료 등록 및 업로드 시 주의해주시기 바랍니다. <br/>
등록·관리에 앞서, 관리자에게 repository 편집 권한을 요청하시기 바랍니다. <br/><br/><br/>

## Lecturer 등록·관리 <br/>
Lecturer 정보는 docs/_data/lecturers.Ymal 파일을 수정하여 등록·관리할 수 있습니다. <br/>
해당 파일에 등록한 정보는, 홈페이지의 Lecturers 페이지에 게시되게 됩니다. <br/>
```yml
- name: "Jhon Doe"
  affiliation: "your affiliation"
  email: "your_email@google.com"
  intro: "your intro" # Optional: 간단한 자기 소개를 입력해주세요.
  photo: "/assets/img/lecturers/your_img.png" # Optional: 해당 란을 비워두면 (""), 기본 이미지가 사용됩니다.
```
photo 등록을 위해서는 docs/assets/img/lecturers 폴더에 사진을 업로드하고, photo: "" 값을 올바르게 수정해주시기 바랍니다. <br/>
Lecturers 페이지에 게시되는 순서는, docs/_data/lecturers.Ymal 파일 내의 순서와 동일하게 정렬되어 게시됩니다. (Lecturer/Special talk의 순서에 맞춰서 정렬하는 것을 권장합니다.) <br/><br/><br/>

## Lecture/Special Talk Event 등록·관리 <br/>
Lecture/Special talk event는 docs/_events 폴더에 .md 파일을 생성·수정하여 등록·관리할 수 있습니다. <br/>
.md 파일의 이름은 홈페이지에 표시되는 내용과 무관합니다. (관리의 용이성을 위해, 파일 이름은 통일된 규칙으로 작성하는 것을 권장합니다.) </br>
```yml
---
layout: event # 이 항목은 수정하지 않습니다.
title: "YOUR_TITLE"
date: 2025-12-25 01:23 +0900
location: "EVENT LOCATION" # Schedule 페이지에서 표시되는 주소
speaker: "EVENT Speakers"
address: "Chungnam National University, 99 Daehak-ro, Yuseong-gu, Daejeon 34134, Korea" # 세부 페이지에서 표시되는 주소
note: "Lecture, Offline, TBA" <!-- Schedule 페이지에서 표시되는 Note -->
overview: > # 세부 페이지에서 표시되는 Overview. Lecture/Special Talk에 대해 간단하게 기술해주세요.
  Brief overview for Lecture/Special talk: Your_TITLE 
timetable: # timetable은 아래와 같은 형태로 기술됩니다.
  - time: "09:00"
    title: "Openning Remarks"
    speaker: "Chair_1"
  - time: "09:30"
    title: "Lecture 1: Introduction"
    speaker: "Lecturer_1"
    material_id: "material_1" # Optional: Lecturer Material 등록·관리에서 설명합니다.
  - time: "10:30"
    title: "Break"
    speaker: ""
  - time: "11:00"
    title: "Lecture 2: Something"
    speaker: "Lecturer_2"
    material_id: "material_2"
  - time: "12:00"
    title: "Lunch"
    speaker: ""
  - time: "16:00"
    title: "Lecture 3: Something Again"
    speaker: "Lecturer_3"
    material_id: "material_3"
  - time: "17:00"
    title: "Discussion"
    speaker: ""
map_embed: > # 세부 페이지에 표시되는 지도. src-"" 부분에 구글 지도에서 원하는 위치를 찍고, 공유-지도 퍼가기-src="" 부분의 링크를 복사하여 붙여넣습니다.
  <iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d1606.3149986890949!2d127.34389919160189!3d36.36974017722345!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x35654bee63320a8f%3A0x70e438ccb2656aa8!2z7Lap64Ko64yA7ZWZ6rWQIOuMgOuNley6oO2NvOyKpA!5e0!3m2!1sko!2skr!4v1758033402650!5m2!1sko!2skr"
          loading="lazy" referrerpolicy="no-referrer-when-downgrade"></iframe>
hero: # Optional: 세부 페이지 상단에 표시되는 이미지와 문구를 지정합니다.
  image: "/assets/img/event_heros/your_hero.png" # 이미지가 등록되어 있지 않으면, 아래의 텍스트 설정과 무관하게 페이지 상단에 이미지·문구가 출력되지 않습니다.
  lines: # 각 문구는 입력 순서에 맞춰 상단->하단 순서로 표시됩니다.
    - text: "YOUR TITLE"
      style: title # 사용 가능한 style은 title, subtitle, text, note, overline 입니다.
    - text: "Speakers"
      style: subtitle
    - text: "2025.00.00 (sat.)"
      style: text
---
```
hero 설정을 위해서는 docs/assets/img/event_heros 폴더에 사진을 업로드하고, image: "" 값을 올바르게 수정해주시기 바랍니다. <br/>
docs/_events 폴더에 .md 파일이 생성되면, Schedule 페이지에 일정 등록 및 세부 페이지가 생성됩니다. <br/>
Schedule 페이지에는 data 값을 기준으로 정렬된 순서로 일정이 표시되며, 각 일정을 클릭하여 세부 페이지에 접근할 수 있습니다. <br/>
.md 파일에 입력된 data 값을 기준으로, 페이지 방문 시점에서 같거나 미래의 일정 중, 가장 가까운 일정이 Next Lecture 페이지에 자동으로 표시됩니다. <br/><br/><br/>

## Lecturer material 등록·관리 <br/>
Lecture material은 /assets/materials 폴더에 pdf 파일을 업로드하고, docs/_data/materials.Ymal 파일을 수정하여 등록·관리할 수 있습니다. <br/>
1. 등록하고자 하는 pdf 파일을 /assets/materials 폴더에 업로드 합니다. (관리의 용이성을 위해, 파일 이름은 통일된 규칙으로 작성하는 것을 권장합니다.) <br/>
2. docs/_data/materials.Ymal 파일을 열어 material의 정보를 입력합니다. <br/>
```yml
- title: "file title" # Lecture Materials 페이지에 표시되는 파일의 이름
  speaker: "author name" # Lecture Materials 페이지에 표시되는 파일의 저자
  date: 2025-09-01 # Lecture Materials 페이지에 표시되는 파일의 날짜
  file: "/assets/materials/file_name.pdf" 
  id: "material_1" # Optional: Lecture/Special talk event 세부 페이지에서 자료 표시를 위한 설정값
```
파일은 홈페이지 접속이 가능한 누구나 열람·다운로드 가능하므로, 열람을 제한하려면 pdf 파일에 비밀번호를 설정하여 업로드하시기 바랍니다. <br/>
pdf 파일에 비밀번호를 설정하는 경우, Lecturer 정보 설정 시 email 항목을 작성하여 자료 열람을 위한 연락이 가능하도록 해주실 것을 강하게 권장드립니다. <br/>
등록된 파일의 title, speaker, date는 Lecture Materials 페이지에 date 순서로 정렬되어 표시됩니다. <br/>
파일의 id는 Lecture/Special talk event 등록·관리시 timetable 내의 material_id 설정에 사용되며, 파일의 id를 material_id에 입력하면 Lecture/Special talk의 세부 페이지 시간표에서 해당 파일이 해당 일정에 함께 표시됩니다.