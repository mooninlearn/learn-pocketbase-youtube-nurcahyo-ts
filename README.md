# learn-pocketbase-youtube-nurcahyo-ts

> [POCKETBASE](https://www.youtube.com/playlist?list=PLusHaWo40rSuvXk4zb3SMnQ8p4AOIhxWV)

> References
- [Picocss Documentation](https://picocss.com/docs/)
- [Picocss Github](https://github.com/picocss/pico)
- [Picocss Theme Default](https://github.com/picocss/pico/blob/master/css/themes/default.css)
- [Picocss > Docs > Customization](https://picocss.com/docs/customization.html)
- [SCSS](https://github.com/picocss/pico/blob/master/scss/pico.slim.scss)

# Install

```bash
# init app
bootapp -u mooninlearn -n learn-pocketbase-youtube-nurcahyo-ts -d "POCKETBASE TUTORIAL https://www.youtube.com/playlist?list=PLusHaWo40rSuvXk4zb3SMnQ8p4AOIhxWV" -t svelte-kit-pico-ts

# install svelte-pocketbase with pnpm, npm or yarn
npm i -D svelte-pocketbase

# build
yarn dev
```


# [POCKETBASE TUTORIAL 1 - LOGIN WITH EMAIL](https://www.youtube.com/watch?v=GQuaf9s4vDA&list=PLusHaWo40rSuvXk4zb3SMnQ8p4AOIhxWV&index=1)
> [Github](https://github.com/bobwatcherx/pocketbaseLoginWithEmail)

## start pocketbase
```bash
cd C:/JnJ-soft/Developments/Database/sqlite
pocketbase serve --dir="./pocketbase-tutorial" --http="127.0.0.1:8090"

# result
Server started at http://127.0.0.1:8090
 ➜ REST API: http://127.0.0.1:8090/api/
 ➜ Admin UI: http://127.0.0.1:8090/_/
```

## Admin login

```
http://127.0.0.1:8090/_/
```

> Admin sign in
```
mooninlearn@gmail.com
```

## Settings / Application
> Settings 버튼(좌측 최하단 Settings 아이콘) 클릭 > System > Application

```
APPLICATION NAME: `PocketbaseTutorial`
APPLICATION URL: `http://127.0.0.1:8090`
```

> `Save changes` 버튼 클릭

## gmail SMTP Server 설정

> [Google - Gmail SMTP 사용을 위한 세팅 ](https://kincoding.com/entry/Google-Gmail-SMTP-사용을-위한-세팅)

> [구글 메일에서 SMTP 설정 방법](https://chasos.tistory.com/38)

> [Gmail SMTP 설정 방법 및 메일 전송](https://hyunmin1906.tistory.com/276)

> [프린터, 스캐너, 앱에서 이메일 보내기](https://support.google.com/a/answer/176600?hl=ko)

- gmail login
- Settings(우측 설정 아이콘) 클릭 > `See all settings` 버튼 클릭 > `Forwarding and POP/IMAP` 탭 클릭
  - POP download: `Enable POP for all mail`
  - IMAP access: 
    - `Enable IMAP`
    - `Auto-Expunge on - Immediately update the server. (default)`
    - `Limit IMAP folders to contain no more than this many messages 1000`

- google account
  - 구글 계정 아이콘(chrome 최상단 아바타 아이콘) 클릭 > `google 계정 관리` 클릭
  - `Security보안`(좌측 메뉴 3번째) 클릭
  - `How you sign in to Google` > `2-Step Verification` 클릭 > `Get started` 클릭
  - `phone number`확인 `Text message` 선택
  - 휴대폰으로 전송된 `Google verification code` 입력
  - smtp.gmail.com
    - SSL: 465
    - TLS: 587

- `2-Step Verification` 클릭 > `App passwords`(최하단) 클릭
- Select app: `Other (Custom name)`
- Select device: `Other (Custom name)`
- `pocketbase` 입력
- `GENERATE` 클릭
- password(`cekgvdaxraguhday`) 복사


## Settings / Mail settings
> Settings > System > Mail settings

```bash
Sender name: `mooninlearn`
Sender address: `mooninlearn@gmail.com`

`Use SMTP mail server (recommended)`
  - SMTP server host: `smtp.gmail.com`
  - Port: `587`
  - Username: `mooninlearn@gmail.com`
  - Password: ``  # App password 입력
```

> `Save changes` 버튼 클릭


# Edit

> `src/routes/+page.svelte`

# Test

```bash
# register / login
http://localhost:5173/
```

## register
- fill in / submit
- email verify
