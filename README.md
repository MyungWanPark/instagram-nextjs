## 주제: Next.js를 활용한 인스타그램 구현
역할 및 범위: 풀스택, 개인 프로젝트

<br/>

> Click the link to see website.&nbsp;&nbsp; [인스타그램](https://instogram-nextjs.vercel.app) <br/>
(Guest 모드를 클릭하면 빠른 로그인 가능합니다.)
<br/>

<details open="close">
<summary>Skills Used</summary>

<br/>

<img src="https://img.shields.io/badge/TypeScript-3178C6?style=flat&logo=TypeScript&logoColor=white" /> 
<img src="https://img.shields.io/badge/Next-000000?style=flat&logo=nextdotjs&logoColor=white" />
<img src="https://img.shields.io/badge/React-3998B6?style=flat&logo=react&logoColor=white" /> 
<img src="https://img.shields.io/badge/TailwindCSS-38BDF8?style=flat&logo=Tailwind CSS&logoColor=white" />
<img src="https://img.shields.io/badge/Sanity-F36458?style=flat&logo=sanity&logoColor=white" />
<img src="https://img.shields.io/badge/SWR-334155?style=flat&logo=swr&logoColor=white" />
<img src="https://img.shields.io/badge/Vercel-000000?style=flat&logo=vercel&logoColor=white" />
<img src="https://img.shields.io/badge/Next--Auth-8432D9?style=flat" />

- 개발 언어: Typescript 5

- 프레임워크: Next.js 14.1.1

- UI: React 18

- CMS(Content Management System): Sanity 3.30.1
   
- 네트워크 상태관리 라이브러리: SWR 2.2.5

- 배포: Vercel
 
- 인증: Next-Auth 4.24.7

</details>
<br/>

### 상세 설명

총 5개의 페이지로 구성되었습니다.

1. [홈](#홈페이지)

2. [사용자 검색](#사용자-검색-페이지)

3. [새로운 게시물 작성](#새로운-게시물-작성-페이지)

4. [사용자 프로필](#사용자-프로필-페이지)

5. [로그인](#로그인-페이지)

<br/>

### 공통 기능
---
- 사용자 정보가 필요하기 때문에 **로그인**이 필요한 페이지 입니다.

  1. 홈

  2. 새로운 게시물 작성

  3. 자신의 프로필 페이지

<br/>

- (해당 페이지를 로그인 하지 않고 방문할 경우, **Sign In** 페이지로 이동할 수 있게 구현하였습니다.)

<br/>

- 특정 페이지로 이동하면 navbar의 **아이콘 색을 검정색**으로 표현하여 **현재 머물고 있는 페이지를 확인**할 수 있도록 구현하였습니다.

<br/>

### 홈페이지

<br/>

<img width="1280" alt="post list-min" src="https://github.com/MyungWanPark/instogram-nextjs/assets/56289900/c3981b08-08cd-470d-8f1b-239486797a36">

<br/>
<br/>

주요 기능

- 상단에 로그인한 사용자가 팔로잉 하고 있는 **유저들의 목록**을 보여줍니다.
    - 해당 유저를 클릭하면 유저의 **프로필 페이지**로 이동합니다.
  
<br/>

- 자신이 작성하거나 팔로잉한 유저들이 작성한 **게시물**을 보여줍니다. <br/>
(demo 에서는 효과적으로 시연하기 위해 모든 게시물을 볼 수 있게 구현했습니다.)

<br/>
다음은 게시물 내에서 구현한 기능들입니다.
  
  - 작성자의 아바타 **이미지 및 이름**을 표시하였습니다.

  - **좋아요 및 북마크**를 할 수 있습니다.
  - **좋아요**를 받은 **갯수**를 알 수 있습니다.
  - 설명글을 표시하였습니다.
  - **작성한 시간**을 상대적인 시간으로 나타내였습니다. ex. 2 Days ago
  - 댓글 기능
    - 입력하지 않으면 버튼이 **비활성화** 됩니다.

    - **댓글의 갯수**를 확인할 수 있습니다.
    - 댓글을 입력하면 **즉각적으로 업데이트**가 됩니다.
    - 이미지 또는 view all comments를 누르면 **상세 게시물 페이지**로 이동합니다.
    - 상세 게시물 페이지 기능
      - **좋아요, 북마크** 기능이 있습니다.

      - **댓글**을 남길 수 있습니다.
      - 상세 페이지에서 좋아요, 북마크를 누르면 바깥 페이지도 **즉시 동기화**가 됩니다.

<br/>

### 사용자 검색 페이지

<br/>

<img width="1274" alt="검색 결과" src="https://github.com/MyungWanPark/instogram-nextjs/assets/56289900/03810255-8795-46fd-9021-63d3d94c95b3">

<br/>
<br/>

주요 기능

- 입력란에 아무것도 입력하지 않으면 **전체 사용자**가 나타납니다.

- 각 사용자별 유저명, 사용자 이름, 팔로워 숫자, 팔로잉 숫자를 보여줍니다
- 유저 이름 또는 사용자 이름으로 **검색**할 수 있습니다.
- 유저 이름을 클릭하면, 해당 **유저의 홈페이지**로 이동합니다.

<br/>

### 새로운 게시물 작성 페이지

<br/>

<img width="1276" alt="upload post-min" src="https://github.com/MyungWanPark/instogram-nextjs/assets/56289900/ad6a5403-5a95-4bfd-8557-c8add5209528">

<br/>
<br/>

주요 기능

- 새로운 이미지를 **클릭하여 첨부**하거나, **드래그 앤 드롭으로 첨부** 할 수 있습니다. 이때 드래그 하면 UI를 **파란색으로 강조**하도록 구현하였습니다.

- 이미지를 첨부하면 해당 **이미지를 즉시 확인**해볼 수 있도록 하였습니다.
- 아래에는 사용자가 텍스트를 입력할 수 있습니다.
- publish 버튼을 누르면 작성이 **완료**됩니다.
- 작성이 완료되면 사용자를 **홈 경로로 이동**시키고, 새로운 게시물을 **피드에서 확인**할 수 있습니다.

<br/>

### 사용자 프로필 페이지

<br/>

<img width="1276" alt="profile image-min" src="https://github.com/MyungWanPark/instogram-nextjs/assets/56289900/c86cd247-91c8-4aaf-871e-de9d282fc82d">

<br/>
<br/>
유저 프로필 페이지 이동 방법 2가지

<br/>

1. 홈페이지에서 **팔로잉 목록에 있는 사용자를 클릭**하면 해당 사용자의 프로필 페이지로 이동합니다.

2. **네비게이션에서 사용자 이미지를 클릭**하면 로그인한 사용자의 프로필 페이지로 이동합니다.

<br/>

주요 기능

- 사용자 검색을 통해 들어간 사용자 페이지에서 **팔로우, 언팔로우** 버튼을 누를 수 있습니다.

- 팔로우, 언팔로우 버튼을 누르면 **follwers** 숫자가 증가하거나, 감소합니다.
- 사용자의 아바타 이미지, 이름, 게시물 갯수, 팔로워, 팔뢰잉 갯수를 알 수 있습니다.
- 다음과 같은 게시물 목록을 볼 수 있습니다.
   -    본인이 **작성한** 게시물 목록
   -    **북마크**로 저장한 게시물 목록
   -    **좋아요**를 누른 게시물 목록
- 해당 게시물을 클릭하면 **상세 게시물**이 나옵니다.
- 모달창의 바깥 버튼을 누르면 모달이 지워집니다.

<br/>

### 로그인 페이지

<br/>

<img width="1276" alt="login_page-min" src="https://github.com/MyungWanPark/instogram-nextjs/assets/56289900/40a12b10-44fc-41c4-bacb-6554986da984">

<br/>
<br/>

주요 기능

- **Guest, Google, Kakao** 계정으로 소셜 로그인 할 수 있습니다. <br/>

- **Guest** 로그인은 빠른 로그인을 위한 기능입니다. 별도의 인증을 하지 않아도 게스트로 로그인 할 수 있습니다.

<br/>

**로그인 권한이 필요한 페이지**

1. 홈

2. 새로운 게시물 작성

3. 자신의 프로필 페이지)

1~3 번의 페이지에 **로그인 하지 않는 상태로 접근한다면** 로그인 페이지로 **redirect** 되도록 구현하였습니다.
