# 수면 기록

취침·기상 시간, 낮잠, 메모, 몸무게를 기록하고 폰과 PC에서 같은 기록을 보는 앱입니다.
앱 화면은 GitHub Pages에, 기록은 본인의 GitHub **비공개** 저장소에 저장됩니다. 별도 서버나 유료 서비스가 필요 없습니다.

처음 설정은 PC에서 하시는 것이 편합니다. 15분 정도 걸립니다.

---

## 1. 앱 저장소 만들고 파일 올리기

1. github.com에 로그인한 뒤 오른쪽 위 **+** → **New repository** 를 누릅니다.
2. Repository name에 `sleep-log` 를 넣고 **Public** 을 고릅니다.
   무료 GitHub Pages는 공개 저장소에서만 켜집니다. 공개되는 것은 앱 화면 파일뿐이고, 기록은 3번에서 만드는 비공개 저장소에 따로 저장됩니다.
3. **Add a README file** 에 체크하고 **Create repository** 를 누릅니다.
4. 저장소 화면에서 **Add file** → **Upload files** 를 누르고, 압축을 푼 파일 8개를 모두 끌어다 놓습니다.
   `index.html`, `sw.js`, `manifest.webmanifest`, `icon-192.png`, `icon-512.png`, `icon-maskable-512.png`, `apple-touch-icon.png`, `README.md`
5. 아래 **Commit changes** 를 누릅니다.

## 2. GitHub Pages 켜기

1. `sleep-log` 저장소에서 **Settings** → 왼쪽 메뉴 **Pages** 로 갑니다.
2. **Build and deployment** 의 Source를 **Deploy from a branch** 로, Branch를 **main** / **(root)** 로 고르고 **Save** 를 누릅니다.
3. 1~2분 뒤 같은 화면 위쪽에 앱 주소가 나옵니다.
   `https://사용자명.github.io/sleep-log/`

## 3. 기록 저장소 만들기 (비공개)

1. 다시 **+** → **New repository** 를 누릅니다.
2. Repository name에 `sleep-data` 를 넣고 반드시 **Private** 을 고릅니다.
3. **Add a README file** 에 체크하고 **Create repository** 를 누릅니다.

## 4. 접근 토큰 만들기

앱이 `sleep-data` 저장소 하나에만 기록을 읽고 쓸 수 있게 해 주는 열쇠입니다.

1. 오른쪽 위 프로필 사진 → **Settings** → 왼쪽 맨 아래 **Developer settings** 로 갑니다.
2. **Personal access tokens** → **Fine-grained tokens** → **Generate new token** 을 누릅니다.
3. 다음과 같이 넣습니다.
   - Token name: `수면 기록 앱`
   - Expiration: 원하는 기간 (만료되면 새 토큰을 만들어 앱에 다시 넣으면 됩니다)
   - Repository access: **Only select repositories** → `sleep-data` 선택
   - Permissions: **+ Add permissions** 를 눌러 **Contents** 를 고르고, 접근 수준을 **Read and write** 로 바꿉니다.
     (예전 화면이라면 Repository permissions 목록에서 Contents를 찾아 Read and write로 바꾸면 됩니다.)
4. **Generate token** 을 누르고 `github_pat_` 로 시작하는 값을 복사해 둡니다.
   이 화면을 벗어나면 다시 볼 수 없으니, 폰에도 넣을 때까지 메모장 등에 잠시 보관해 주십시오.

## 5. 앱 연결하기 (기기마다 한 번)

1. 앱 주소를 열고 **설정** 으로 갑니다.
2. GitHub 사용자명, 저장소 이름(`sleep-data`), 토큰, 이 기기 이름(예: 집 PC)을 넣고 **연결 확인 후 저장** 을 누릅니다.
3. "마지막 동기화" 문구가 보이면 연결된 것입니다.
4. 폰에서도 같은 주소를 열어 똑같이 넣어 주십시오.

## 6. 홈 화면에 앱으로 설치하기

- **iPhone (Safari)**: 공유 버튼 → **홈 화면에 추가**
  iPhone은 홈 화면 앱과 Safari의 저장 공간이 따로입니다. 홈 화면에 추가한 **앱 안에서** 5번 연결을 해 주십시오.
- **Android (Chrome)**: 오른쪽 위 ⋮ → **앱 설치** 또는 **홈 화면에 추가**
- **PC (Chrome·Edge)**: 주소창 오른쪽의 설치 아이콘 → **설치**

---

## 사용법

- **오늘**: `지금 잠` → 아침에 `지금 일어남`. 낮잠은 누르기 전에 위의 `낮잠` 을 고릅니다. 오전 9시~오후 6시에는 낮잠이 미리 선택됩니다.
- **잘못 눌렀을 때**: 아래에 뜨는 알림의 `되돌리기`, 또는 기록 옆 연필 버튼으로 시간을 고칩니다.
- **깜빡했을 때**: `+ 빠뜨린 기록 직접 추가`
- **기록 유무**: 날짜 아래 점 3개가 수면(파랑)·메모(회색)·몸무게(초록)를 뜻합니다. 날짜 제목을 누르면 한 달 달력이 열립니다.
- **수면 그래프**: 하루·일주일·한달·연간. 취침(위)과 기상(아래)을 함께 봅니다. `전체 화면` 으로 크게 볼 수 있고, PC에서는 모든 꼭짓점에 시간이 표시됩니다. 폰의 한달 그래프는 점을 누르면 시간이 보입니다.
- **몸무게**: 오늘 화면이나 몸무게 탭에서 넣습니다. 지난 날짜도 고를 수 있습니다.
- **설정**: 배경색(흰색·카키·네이비), 백업 파일 받기·불러오기, 예시 데이터로 둘러보기.

## 계산 기준

- 밤잠은 **일어난 날짜**에 들어갑니다. 11/7 23:40에 자고 11/8 07:10에 일어나면 11/8 기록입니다.
- 낮잠은 잠든 날짜에 들어갑니다.
- 총 수면 = 밤잠 + 낮잠
- 활동시간 = 그날 기상 시각부터 그날 밤 취침 시각까지
- 취침 그래프의 세로축은 저녁 시간부터 시작해서 자정이 가운데 오도록 그립니다. 연간 그래프는 월별 평균입니다.

## 기록 파일과 동기화

- 기록은 `sleep-data` 저장소의 `data/2026.json` 처럼 연도별 파일로 저장됩니다. GitHub에서 직접 열어 볼 수 있습니다.
- 인터넷이 끊겨도 기록은 기기에 먼저 저장되고, 연결되면 자동으로 올라갑니다.
- 폰과 PC에서 동시에 고쳐도 항목마다 나중에 고친 내용이 남습니다.

## 보안

- 토큰은 그 기기의 브라우저 안에만 저장되며, `sleep-data` 저장소 하나만 다룰 수 있습니다.
- 기기를 잃어버렸다면 GitHub → Settings → Developer settings → Fine-grained tokens에서 그 토큰을 삭제해 주십시오.

## 앱을 고쳐서 다시 올릴 때

바뀐 파일을 1번과 같은 방법으로 올린 뒤, `sw.js` 맨 위의 `sleeplog-v1` 숫자를 하나 올리면(`sleeplog-v2`) 각 기기에 새 버전이 빨리 반영됩니다.
