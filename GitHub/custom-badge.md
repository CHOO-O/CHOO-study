# 커스텀 뱃지 만들기

메인 Readme를 꾸미던 도중 문득 생각이 들었다.<br>

티스토리나 Velog, Github.io를 이용해 개인 블로그를 운영하시는 분들은 많이들 업로드한 최신 글을 보여주는 뱃지를 달아두곤 한다.<br>

하지만 나는 따로 꾸며진 블로그를 작성하는게 아닌 레포지토리에 직접적으로 md파일을 작성해서 올리는 방식을 사용하고 있다.<br>

나도... 나도 내가 블로그 쓴거 자랑하고 싶다!! <br>

그래서 백준이나 프로그래머스 뱃지처럼 Github에서 제공하는 API와 Git Actions를 활용해 커스텀 뱃지를 만들어보려고 한다.

### 첫 번째 계획

1. 블로그 레포지토리의 `main` 브랜치에 `push` 작업이 일어날 때, 최근 커밋에서 변경된 `.md` 파일이 있는지 탐색한다.
2. 있을 경우 해당 파일의 첫 번째 줄을 추출해 제목을 만들고, 커밋 날짜를 `YYYY/MM/DD` 형식으로 추출한다.
3. 이를 반영한 `svg` 파일을 생성해 `CHOO-study/badge`에 저장한다.<br>`<a>태그`를 이용해 누르면 새 탭으로 해당 포스트가 열리도록 한다.
4. 저장된 `svg` 파일을 `CHOO-O/README.md` 에서 가져온다.

그러나, GitHub의 보안 정책으로 인해 `svg` 파일 내의 `<a>태그` 가 동작하지 않았다.<br>

### 두 번째 계획

1. 블로그 레포지토리의 `main` 브랜치에 `push` 작업이 일어날 때, 최근 커밋에서 변경된 `.md` 파일이 있는지 탐색한다.
2. 있을 경우 해당 파일의 첫 번째 줄을 추출해 제목을 만들고, 커밋 날짜를 `YYYY/MM/DD` 형식으로 추출한다.
3. 이를 반영한 `svg` 파일을 생성해 `CHOO-study/badge`에 저장한다.<br>더하여, 추출한 변수를 활용해 최신 글의 링크를 생성한 `txt`파일을 함께 저장한다.
4. 파일이 성공적으로 생성되면, Personal Access Token(PAT)을 통해 `CHOO-study`에 자동 커밋 후, 기본 레포지토리에 `repository_dispatch` 이벤트를 전송한다.
5. 기본 레포지토리에서는 해당 이벤트를 감지하여 워크플로우를 수행하고, 전달받은 `svg`와 `txt` 파일을 반영한다.
6. README 내의 `<!--LATEST_LINK_START--> ~ <!--LATEST_LINK_END-->` 영역을 수정하며, 기존 링크와 동일할 경우 커밋을 생략한다.

### 예외처리한 부분

1. `README.md`, `Rules.md`, `badge/` 하위의 파일은 `.md` 파일 변경 대상에서 제외된다.
2. `.md` 파일이 아닌 파일만 수정된 경우, 워크플로우는 실행되지 않으며 `skip` 처리가 된다.
3. 변경사항이 없는 경우 새로 `svg`/`txt` 파일을 생성하지 않음으로써 불필요한 커밋을 방지한다.

### 후기

일단은 GPT의 도움과 함께 어떻게든 만들긴 했다!<br>
하지만 제대로 되는 듯 하다가도 오류가 발생하고 있는걸 보니... 꾸준히 수정을 해 줘야 할 것 같다...

🔗 [CHOO-study의 workflow](https://github.com/CHOO-O/CHOO-study/blob/main/.github/workflows/latest-post-badge-generate.yml)

🔗 [CHOO-O의 workflow](https://github.com/CHOO-O/CHOO-O/blob/main/.github/workflows/update-badge.yml)
