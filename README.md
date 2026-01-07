# React Storybook 디자인 협업
Chromatic을 활용한 React Storybook 디자인 협업
## 목적
1. Storybook에 로드되는 모든 컴포넌트, 스타일 변경 추적
2. 수정 컴포넌트, 스타일 육안 확인
3. Build & Accept 과정, 피드백을 통해 UI 품질 보장/향상
## 개발환경
1. IDE
	1) VS Code
3. 개발언어
	1)TypeScript
3. API / 라이브러리
	1) React
	2) Storybook
	3) Chromatic
4. 빌드도구
	1) Vite
## 가이드
1. Vite로 React+Typescript 프로젝트 생성
	1) npm create vite@latest [project_name]
	2) typescript 선택
2. Storybook 설치
	1) StoryBook 설치
		- npx storybook@latest init 
	2) Storybook 설정 자동 초기화
		- npx sb init
	3) Storybook 실행 (node.js 18버전 이상)
		- npm run storybook
	4) Storybook addone 설치
		- npm install @storybook/addon-designs --save-dev
	5) Storybook 실행
		- npm run build-storybook
3. Chromatic 설치
	1) Chromatic 설치 
		- npm install -D chromatic
	2) Chromatic 사이트 접속
		- https://www.chromatic.com/start?utm_source=storybook_website&utm_medium=link&utm_campaign=storybook
	3) 깃 계정 인증
	4) 사용할 깃 레포지토리 선택
	5) storybook 선택
	6) storybook 빌드
		- npm run build-storybook
	7) 프로젝트 root 폴더에 root/.github/workflows 디렉토리 생성
	8) workflows폴더에 chromatic.yml 파일 생성 (CI/CD 파이프라인, 빌드 속도 향상)
	9) git repository secret 등록
		- projectToken secret관리를 위해 깃허브 repository > Settings > Secret and Valriables > Action > Repository secret > New repository secret 버튼 클릭
			. Name : CHROMATIC_PROJECT_TOKEN
			. Secret : 위에서 부여 받은 project-token 입력
4. 버전 관리
	1) Git 반영
		. git pull & push
	2) Chromatic 반영 (CI/CD 파이프라인 구축 시, 명령어 실행 불필요)
		- npx chromatic --project-token=[project-token]
5. 동작화면
	1) 버튼 추가
		<img width="339" height="936" alt="1_redbutton추가" src="https://github.com/user-attachments/assets/60019e43-5a43-413e-91b6-e5a65653db88" />
	3) Chromatic 프로젝트 인증
		<img width="839" height="689" alt="2_chromatic 인증" src="https://github.com/user-attachments/assets/6aa486a8-61ec-412c-8145-0286741cf9d1" />
	4) Chromatic 사이트 접속
		<img width="2537" height="877" alt="3_Chromatic 사이트 접속" src="https://github.com/user-attachments/assets/4f90b058-7d0d-4701-825a-c5e1421e59be" />
	5) 빌드 확인
		<img width="2320" height="1289" alt="4_Chromatic 반영_빌드페이지" src="https://github.com/user-attachments/assets/1975cdab-ef0d-44e1-b9ec-2eab27bd5f3a" />
	6) View Storybook
		<img width="2360" height="1147" alt="5_view storybook 클릭시_storybook확인" src="https://github.com/user-attachments/assets/f09aeda4-b4dc-46a1-8f8a-264ecd9ba417" />
	7) Verify (변경 UI 확인)
		<img width="2523" height="1159" alt="6_verify 클릭시_변경UI확인" src="https://github.com/user-attachments/assets/f0baca47-65cf-4cef-86fc-5972350597d6" />
	8) Accept (반영)
		<img width="2514" height="1240" alt="7_accept 클릭시_정상반영" src="https://github.com/user-attachments/assets/381cbf39-05ad-43d5-a618-b149cda3f07d" />
	9) View changes 비교
		<img width="2533" height="958" alt="8_(별도)_view changes 비교" src="https://github.com/user-attachments/assets/7e9d397c-8af1-4bff-ab0c-e335aa276063" />





