# 스터디 설명서

## 스터디 가이드라인
[Airbnb 코드스타일 가이드 바로가기](https://github.com/tipjs/javascript-style-guide#28.2 "Airbnb 코드스타일 가이드")


---
## 목차

  1. [레포지토리 세팅방법](#레포지토리-세팅방법)
     1. [바이너리서당 깃허브에 접속](#바이너리서당-깃허브에-접속)
  
---

## 레포지토리 세팅방법
   #### 바이너리서당 깃허브에 접속
[바이너리서당 바로가기](https://github.com/orgs/binary-seodang/repositories "바이너리서당 레포지토리 바로가기")
   #### 필터 타입을 templates로 변경
![필터타입변경](https://kitworks.s3.ap-northeast-2.amazonaws.com/codereview/%ED%85%9C%ED%94%8C%EB%A6%BF%ED%95%84%ED%84%B0%EC%84%A4%EC%A0%95.png)
   #### 원하는 template을 선택 후 clone하기
   |템플릿 목록||
   |----|----|
   |![템플릿목록](https://kitworks.s3.ap-northeast-2.amazonaws.com/codereview/%ED%85%9C%ED%94%8C%EB%A6%BF+%EB%AA%A9%EB%A1%9D.png)|<ul><li style="margin-bottom:5px;"><a href="https://github.com/binary-seodang/vite-react-javascript" target="_blank">vite react-js</a></li><li style="margin-bottom:5px;"><a href="https://github.com/binary-seodang/vite-react-typescript">vite react-ts</a></li><li style="margin-bottom:5px;"><a href="https://github.com/binary-seodang/default" target="_blank" >empty js</a></li><li style="margin-bottom:5px;"><a href="https://github.com/binary-seodang/nestjs" target="_blank">nestjs</a></li><li style="margin-bottom:5px;"><a href="https://github.com/binary-seodang/next-javascript" target="_blank">next-js</a></li><li style="margin-bottom:5px;"><a href="https://github.com/binary-seodang/next-typescript" target="_blank">next-ts</a></li></li><li style="margin-bottom:5px;"><a href="https://github.com/binary-seodang/react-javascript" target="_blank">CRA-js</a></li><li style="margin-bottom:5px;"><a href="https://github.com/binary-seodang/react-typescript" target="_blank">CRA-ts</a></li>
</ul>
   
#### 패키지 설치 후 아래 이미지와 같은 메세지가 노출 된다면 성공
   ```bash
   npm install # yarn
   ```
   ![성공메세지](https://kitworks.s3.ap-northeast-2.amazonaws.com/codereview/husky_install.png)

#### git 원격 주소가 이미 등록되어 있는 상태이므로 원격주소지 제거 및 재등록
   ```bash
   git remote remove origin
   git remote add origin <<자신의 원격 레포지토리 주소>>
   ```

#### 작업한 소스들을 스테이징에 올리고 '커밋' 버튼 클릭
   ![커밋버튼설명](https://kitworks.s3.ap-northeast-2.amazonaws.com/codereview/%EC%8A%A4%ED%85%8C%EC%9D%B4%EC%A7%95.png)

#### 원격 최초 연결이 완료되었다면, 원격 레포지토리 세팅
   - 레포지토리 세팅
      ![레포지토리세팅](https://kitworks.s3.ap-northeast-2.amazonaws.com/codereview/%EC%9B%90%EA%B2%A9%EC%B4%88%EA%B8%B0%EC%84%B8%ED%8C%85.png)
   - 콜라보레이터 추가
      ![콜라보레이터추가](https://kitworks.s3.ap-northeast-2.amazonaws.com/codereview/%EC%BD%9C%EB%9D%BC%EB%B3%B4%EB%A0%88%EC%9D%B4%ED%84%B0%EC%B6%94%EA%B0%80.png) 
   - 브런치 규칙 추가
      ![브런치규칙추가](https://kitworks.s3.ap-northeast-2.amazonaws.com/codereview/%EB%B8%8C%EB%9F%B0%EC%B9%98%EA%B7%9C%EC%B9%99%EC%B6%94%EA%B0%80.png) 
   - 체크 된 브런치 규칙 확인
      ![브런치룰1](https://kitworks.s3.ap-northeast-2.amazonaws.com/codereview/%EB%B8%8C%EB%9F%B0%EC%B9%98%EB%A3%B0.png) 
      ![브런치룰2](https://kitworks.s3.ap-northeast-2.amazonaws.com/codereview/%EB%B8%8C%EB%9F%B0%EC%B9%98%EB%A3%B02.png) 


---
## 추가 설정
1.  라벨 설정하기
    - YOUR_GH_TOKEN : 깃허브 Personal access token [깃허브 토큰발급 바로가기](https://github.com/settings/apps)
    - YOUR_REPOSITORY : 해당하는 레포지토리 경로 ex) myname/myProject
    ```bash
    npx github-label-sync --access-token <<YOUR_GH_TOKEN>> --labels ./labels.json <<YOUR_REPOSITORY>>
    ```
2.  커밋 템플릿 적용하기
      ```bash
      git config --global core.editor "code --wait"   # 깃 에디터를 vscode로 변경
      git config --global commit.template <.gitmessage.txt 경로>
      ```

---

## 커밋 컨벤션

- 템플릿
  ```
  🎨feat : 기능 추가 및 개선
  🐛fix : 오류 수정
  💄style : 코드의 수정이 없는 문자포멧팅
  🧪test : 코드 및 기능 테스트
  ♻️refactor : 기존 코드를 수정한 코드정리
  🗑️cleanup : 기존 코드를 수정하지 않은 코드정리
  🚧chore : 환경설정 및 프로젝트 세팅
  ```
- regex
  - ^(🎨|🐛|💄|♻️|🗑️|🚧|🧪)(feat|fix|style|refactor|cleanup|chore|test)\s:\s.+
- 유다시티 커밋컨벤션
  ```HTML
  <type>(<scope>): <subject> - Subject line
  <BLANK LINE> - 줄 바꿈으로 구분한다
  <body> - Message body
  <BLANK LINE>  
   <footer> - Message footer

      1. **Subject line**
         1. 변경 사항에 대한 간단한 설명.
      2. **Message body**
         1. 수정 이유와 전후 비교 설명.
         2. 명령형 현재 시제로 작성한다. (changed X, change O)
      3. **Message footer**
         1. 주요 변경사항은 푸터에 변화에 대한 상세설명, 정의, 이전 노트와 함께 명시되어야 한다.
         2. 전후를 Before : scope: { ~~ } After : scope: { ~~~ } 와 같이 상세하게 명시한다.
         3. 처리 완료된, 즉 close 된 이슈에 대해서는 `Closes #123, #124` 로 표기한다.
---
