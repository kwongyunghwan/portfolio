# 권경환의 포트폴리오

# 1. 영목사(영화 목록 보여주는 사이트)
## 프로젝트 개요
영목사(영화 목록 보여주는 사이트)는 TMDB API를 활용하여 실시간 영화 정보를 제공하는 영화 검색 및 추천 서비스입니다. 사용자는 장르별, OTT별 필터링을 통해 원하는 영화를 쉽게 찾을 수 있으며, Carousel UI로 직관적인 영화 탐색 경험을 제공합니다.

- **개발기간:** 2024.11.10 ~ 2024.12.28 (약 2개월)
- **링크:**  [프로젝트 코드 및 상세설명](https://github.com/kwongyunghwan/movie)

## 실제 화면

<img width="800" height="600" alt="image" src="https://github.com/user-attachments/assets/c66f86fc-8be1-4a56-a53c-dd97d97199c1" />

## 기술 스택 및 기능

### Back-end

![Node.js](https://img.shields.io/badge/Node.js-339933?style=flat-square&logo=node.js&logoColor=white)
![Express](https://img.shields.io/badge/Express-000000?style=flat-square&logo=express&logoColor=white)
![NodeCache](https://img.shields.io/badge/NodeCache-68A063?style=flat-square&logo=nodedotjs&logoColor=white)
![Axios](https://img.shields.io/badge/Axios-5A29E4?style=flat-square&logo=axios&logoColor=white)

**주요 기능 및 구현**

- **Express 5 RESTful API 서버 구축**
  - 8개 엔드포인트 개발 (영화 목록, 상세, 검색, 장르, OTT)
  - TMDB API 통합 및 데이터 가공
  - 한국 개봉일 및 OTT 제공 정보 추가
  
- **NodeCache를 활용한 서버 캐싱**
  - 응답 속도 향상
  - TTL 10분 설정으로 최신 데이터 유지
    
**데이터 흐름:**
```
React Client → Express 서버 → NodeCache 확인
→ (캐시 없음) TMDB API 호출 → 데이터 가공
→ NodeCache 저장 → JSON 응답
```
### Front-end
![React](https://img.shields.io/badge/React-61DAFB?style=flat-square&logo=react&logoColor=black)
![React Router](https://img.shields.io/badge/React_Router-CA4245?style=flat-square&logo=react-router&logoColor=white)
![Framer Motion](https://img.shields.io/badge/Framer_Motion-0055FF?style=flat-square&logo=framer&logoColor=white)
![CSS Modules](https://img.shields.io/badge/CSS_Modules-000000?style=flat-square&logo=css3&logoColor=white)

**주요 기능 및 구현**

- **Framer Motion 3D Carousel**
  - 마우스 드래그로 3D 효과
  - 부드러운 애니메이션 전환

- **장르/OTT 다중 필터링 시스템**
  - 여러 장르와 OTT 동시 선택 (액션, 코미디, 넷플릭스, 웨이브 등)
  - URL 쿼리스트링으로 필터 상태 유지

- **영화 상세 모달**
  - 평점, 개봉일, 러닝타임, 장르 정보 표시
  - 한국 개봉일 및 OTT 제공 정보
  - YouTube/Vimeo 예고편 링크

- **통합 검색 및 성능 최적화**
  - 모든 페이지에서 실시간 검색
  - useMemo로 필터링 결과 메모이제이션
  - useCallback으로 함수 재생성 방지
  - CSS Modules로 반응형 UI 구현
    
 **사용자 흐름도:**
```
페이지 접속 → 필터 선택 → 영화 카드 클릭
→ 모달 표시 → 예고편 시청
```

---
# 2. 나만의 북마크 관리

## 프로젝트 개요

고유 코드를 통해 북마크를 생성하고 공유할 수 있는 웹 애플리케이션입니다. 사용자는 8자리 코드로 자신만의 북마크 페이지를 만들고, 링크와 이미지를 추가하여 관리할 수 있습니다.

- **개발 기간** : 2024.10.15 ~ 2024.11.09 (1개월)
- **링크:** [프로젝트 코드 및 상세설명](https://github.com/kwongyunghwan/bookmark)

## 실제 화면

<img width="800" height="600" alt="image" src="https://github.com/user-attachments/assets/76b8c65f-27a4-49c0-b95a-96924d906d3a" />

## 기술 스택 및 기능
### Back-end
![Next.js](https://img.shields.io/badge/Next.js-000000?style=flat-square&logo=next.js&logoColor=white)
![MongoDB](https://img.shields.io/badge/MongoDB-47A248?style=flat-square&logo=mongodb&logoColor=white)
  
**주요 기능 및 구현**

- **API Routes API 개발**
  - RESTful API 설계 (GET, POST, PATCH, DELETE)
  - FormData를 이용한 이미지 파일 처리
  - 북마크 코드 기반 데이터 조회/저장/수정/삭제

- **MongoDB 데이터베이스 관리**
  - 북마크 데이터 스키마 설계
  - 북마크 코드별 데이터 필터링
  - 글로벌 연결 캐싱으로 DB 연결 최적화

- **파일 시스템 관리**
  - FormData를 통한 이미지 업로드 및 저장
  - 파일명 중복 방지 (타임스탬프 활용)
    
**데이터 흐름:**
```
Client → API Routes → MongoDB 조회
→ (POST) FormData 파일 추출 → 파일 시스템 저장
→ MongoDB에 경로 저장 → JSON 응답
```

### Front-end
![React](https://img.shields.io/badge/React-61DAFB?style=flat-square&logo=react&logoColor=black)
![Redux](https://img.shields.io/badge/Redux-764ABC?style=flat-square&logo=redux&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=flat-square&logo=css3&logoColor=white)

**주요 기능 및 구현**
- **고유 북마크 코드 생성**
  - crypto로 8자리 랜덤 코드 생성

- **이미지 업로드 및 미리보기**
  - 파일 선택 시 이미지 미리보기
  - FormData로 이미지 파일 전송
    
- **컴포넌트 기반 설계**
  - 북마크 카드 컴포넌트
  - 추가/수정 모달 컴포넌트

- **Redux Toolkit 상태 관리**
  - 북마크 코드 전역 상태 관리
  - Redux Persist로 새로고침 시에도 상태 유지

- **북마크 코드 공유**
  - Clipboard API로 코드 복사
  - 코드 입력으로 다른 사용자의 북마크 접속
    
**사용자 인터랙션:**
```
메인 페이지 → 코드 생성/입력 → 북마크 관리
→ 추가 → 수정/삭제 → 공유
```
---
# 3. 상담서버 구축 프로젝트(PL)

## 프로젝트 개요
실시간으로 고객 상담 요청을 처리하고 상담원의 효율적인 관리를 지원하는 **통합 상담 서버 시스템**을 구축하는 것을 목표로 합니다. 이 시스템을 통해 상담원은 유입되는 고객의 상담 요청을 즉시 확인하고 수락하여 원활하게 상담을 진행할 수 있으며, 관리자는 전용 관리 기능을 통해 실시간으로 상담원들의 활동 상태 및 전체 상담 현황을 직관적으로 모니터링하고 효과적으로 관리할 수 있는 프로젝트입니다.

- **개발기간:** 2022.03.31 - 2022.08.30(5개월)
- **프로젝트 인원** 백엔드 1명, 프론트엔드 2명, 풀스택 1명(총 4명)
- **나의 역할:** 조장으로서 전반적인 진행상황과 개발 일정 관리 및 팀원 간의 업무조율을 했으며 풀스택 개발자로서 Socket.io를 활용한 실시간 채팅 기능 개발부터 React를 이용한 채팅 화면 및 대화 이력 페이지 구현을 담당했습니다.
- [프로젝트 코드 및 상세설명](https://github.com/kwongyunghwan/agentServer)

## 실제 화면
<img width="1510" height="696" alt="image" src="https://github.com/user-attachments/assets/dad54a82-2a86-440f-93a9-618db6f35c8d" />

## SW 구성도
![image](https://github.com/user-attachments/assets/277968b0-f5a7-4660-9460-3eb2fe3592e8)

고객의 상담 요청이 소켓을 통해 실시간으로 **상담 서버**에 전달되고, 서버는 이 요청을 **React 기반의 상담원 페이지**에 표시하며 상담원이 수락 후 상담을 진행하는 구조입니다.
관리자는 별도의 **React 기반 관리자 페이지와 서버 통신**을 통해 **실시간 현황을 모니터링하고 관리**하며, 모든 데이터는 MongoDB에 저장됩니다.

## 기술 스택 및 기능
### Back-end
![Node.js](https://img.shields.io/badge/Node.js-339933?style=flat-square&logo=node.js&logoColor=white)
![Express](https://img.shields.io/badge/Express-000000?style=flat-square&logo=express&logoColor=white)
![Socket.io](https://img.shields.io/badge/Socket.io-010101?style=flat-square&logo=socket.io&logoColor=white)
![MongoDB](https://img.shields.io/badge/MongoDB-47A248?style=flat-square&logo=mongodb&logoColor=white)

**주요 기능 및 구현**
- **Socket.IO 기반 실시간 통신 개발**
  - 채팅방 입장/나가기 이벤트 처리
  - 메시지 송수신 및 브로드캐스팅
  - 60초 무응답 시 자동 종료 타임아웃 로직

- **MongoDB 데이터 저장 및 관리**
  - 채팅방, 메시지, 사용자 스키마 설계
  - 채팅 이력 저장 및 조회 API
  - 상담 메모 저장 기능

- **Express API 서버 구축**
  - 로그인/회원가입 인증 API
  - 상담원 목록 조회 및 관리 API
  - 상담 이력 조회 API (검색, 정렬, 페이지네이션)
  - 프로필 사진 업로드 API (Multer)

### Front-end

![React](https://img.shields.io/badge/React-61DAFB?style=flat-square&logo=react&logoColor=black)
![Recoil](https://img.shields.io/badge/Recoil-3578E5?style=flat-square&logo=recoil&logoColor=white)
![Styled Components](https://img.shields.io/badge/Styled_Components-DB7093?style=flat-square&logo=styled-components&logoColor=white)
![Axios](https://img.shields.io/badge/Axios-5A29E4?style=flat-square&logo=axios&logoColor=white)

#### Front-end 파트 설명 (Front-end)
- **React.js 기반 채팅 UI 개발**
  - 실시간 메시지 표시 및 자동 스크롤
  - 대기/상담중 채팅방 목록 (탭 UI)
  - 메시지 입력창 및 전송 버튼
  - 채팅방 나가기 기능

- **Recoil 전역 상태 관리**
  - 메시지 리스트 상태 관리
  - 상담원 정보 상태 관리
  - SessionStorage와 연동하여 새로고침 시에도 상태 유지

- **상담 이력 페이지**
  - 전체 상담 이력 조회
  - 방 번호/상담원 검색 기능
  - 시작일시/종료일시 정렬
  - React-js-pagination 라이브러리 활용

- **마이페이지**
  - 프로필 사진 업로드 및 변경
  - 전화번호 수정 모달
  - 나의 상담 이력 조회

- **관리자 기능 (권한별 접근 제어)**
  - 상담원 목록 관리
  - 권한 변경 (admin/agent/reader)
  - 접속 상태 표시 (온라인/오프라인)
    
---
# 4. 안전모야 부탁해(Oh hat) 프로젝트

## 프로젝트 개요

'안전모야 부탁해(Oh hat)' 프로젝트는 인부들의 안전을 위해 안전모에 부착된 **센서 데이터를 서버로 전송**하여, 관제센터 페이지에서 **실시간으로 안전모 착용 여부와 온도 측정을 확인**할 수 있도록 개발된 프로젝트입니다. 이를 통해 위험 상황 판단 및 즉각적인 대응을 위한 Q&A 기능을 지원합니다.

- **개발기간:** 2020.05.25 - 2020.10.31
- **프로젝트 인원** 백엔드 1명, 웹개발 1명, 앱개발 1명, IOT개발 2명(총 6명)
- **나의 역할:** 웹 개발을 담당하였으며 아래 기능을 구현했습니다.
  - 관제센터 모니터링 페이지 구현
  - 실시간 센서 데이터 표시 (안전모 착용 여부, 온도)
  - Q&A 시스템 개발 (질문/답변 CRUD)
  - MySQL 쿼리 작성
- **링크:**  [프로젝트 코드](https://github.com/kwongyunghwan/safety-helmet)

## 실제 화면
<img width="1261" height="611" alt="image" src="https://github.com/user-attachments/assets/59594588-734e-46f2-8f2b-d6b37a267ac6" />

## SW 구성도
![image](https://github.com/user-attachments/assets/5c129232-fd45-425d-ab9c-c42775d0a94a)

## 기술 스택 및 기능
### Back-end
![PHP](https://img.shields.io/badge/PHP-777BB4?style=flat-square&logo=php&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=flat-square&logo=mysql&logoColor=white)
#### Back-end 파트 설명

- **PHP 서버 개발**
  - IoT 센서 데이터 수신 및 처리
  - MySQL 데이터베이스 연동
  - Q&A 시스템 CRUD API
서 데이터 테이블 설계
  - Q&A 테이블 설계
  - 데이터 저장 및 조회 쿼리 작성

- **위험 상황 판단 로직**
  - 안전모 미착용 감지
  - 온도 임계값 초과 감지
  - 알림 트리거 구현
 
### Front-end
![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat-square&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=flat-square&logo=css3&logoColor=white)
![jQuery](https://img.shields.io/badge/jQuery-0769AD?style=flat-square&logo=jquery&logoColor=white)

#### Front-end 파트 설명
- **관제센터 모니터링 페이지**
  - 실시간 센서 데이터 표시
  - 안전모 착용 상태 시각화
  - 온도 그래프 표시
  - 위험 상황 알림 UI

- **Q&A 시스템 UI**
  - 질문 목록 표시
  - 질문 작성 폼
  - 답변 작성 및 표시
  - jQuery를 활용한 비동기 통신

- **반응형 대시보드**
  - HTML/CSS 레이아웃
  - jQuery를 통한 동적 UI 업데이트
    
---

# 5. 실시간 마스크 착용 확인

## 프로젝트 개요

YOLOv5 모델을 활용하여 사람과 동물 등 다양한 데이터셋을 딥러닝 학습시켜 실시간으로 마스크 착용 유무를 확인할 수 있는 커스텀 모델을 개발하는 프로젝트입니다.

- **개발기간**: 2020.11.01 ~ 2020.12.12(1.5개월)
- **링크:** [프로젝트 코드](https://colab.research.google.com/drive/1qtoBiMIDeLlIX9gqT-2c0GO9JZ-a-F-6?usp=sharing#scrollTo=LjWYlvVQmxL8)

## 실제 화면
<img width="588" height="403" alt="image" src="https://github.com/user-attachments/assets/ece08013-8dea-4bc0-a13c-dc055d60542a" />

## 기술 스택
![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![YOLOv5](https://img.shields.io/badge/YOLOv5-00FFFF?style=flat-square&logo=yolo&logoColor=black)
![OpenCV](https://img.shields.io/badge/OpenCV-5C3EE8?style=flat-square&logo=opencv&logoColor=white)
**주요 기능 및 구현**
- **실시간 영상 캡처 및 처리**
  - OpenCV로 웹캠/CCTV 연결 (cv2.VideoCapture)
  - 프레임 단위 실시간 캡처 (FPS: 30)
  - 영상 전처리 (리사이징, 정규화)

- **YOLOv5 추론 결과 시각화**
  - Bounding Box 그리기 (cv2.rectangle)
  - 마스크 착용 여부 레이블 표시 (cv2.putText)
  - 신뢰도 점수 표시 (0.0 ~ 1.0)
  - 색상 구분 (착용: 초록색, 미착용: 빨간색)

- **사용자 인터페이스**
  - OpenCV 윈도우로 실시간 영상 출력
  - ESC 키로 프로그램 종료
    
**실시간 처리 흐름:**
```
웹캠 연결 → 프레임 캡처 → YOLOv5 추론
→ Bounding Box 그리기 → 레이블 표시 → 화면 출력
```
--- 

# 6. 자기 개발 블로그 운영
- 이 블로그는 제가 학습하고 경험한 내용을 정리하고 공유하는 공간이며 Python, Spring, React, Node.js 등 다양한 기술 스택을 활용하여 웹 개발을 하고 있습니다.
- 또한, 자료구조 및 알고리즘 학습을 통해 문제 해결 능력을 꾸준히 향상시키고 있습니다.
- **링크:**[블로그 바로가기](https://velog.io/@roope97/posts)

