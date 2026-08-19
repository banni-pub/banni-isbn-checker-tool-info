# banni-isbn-checker-tool-info

**반니 ISBN 조회기**가 실행할 때마다 한 번 읽어 가는 안내 파일이 여기 있다.
저장소에 있는 파일은 [`version.json`](version.json) 하나뿐이다.

```
https://raw.githubusercontent.com/banni-pub/banni-isbn-checker-tool-info/main/version.json
```

조회기의 `config.txt` 에 있는 `VERSION_CHECK_URL` 이 이 주소를 가리킨다.

---

## 칸이 셋이다

```json
{
  "enabled": true,
  "minVersion": "1.0.0",
  "message": "새 버전으로 업데이트해 주세요."
}
```

| 칸 | 뜻 |
|---|---|
| `enabled` | `false` 로 바꾸면 조회기가 **「이 도구는 더 이상 쓰지 않습니다」**라고 알린다 |
| `minVersion` | 이 값보다 **낮은** 판으로 돌고 있으면 알린다. 같거나 높으면 조용하다 |
| `message` | 위 둘 중 하나라도 걸렸을 때 **그대로 보여 줄 문장** |

고치는 방법은 이 저장소에서 `version.json` 을 편집하고 `main` 에 올리는 것뿐이다.
조회기는 **다음 실행 때** 새 값을 읽는다 — 돌고 있는 창은 그대로다.

---

## ⚠ 이것은 잠금장치가 아니다

**알림일 뿐이다. 조회기는 어떤 경우에도 멈추지 않는다.**

- `enabled: false` 로 두어도 조회는 계속된다 — 문구만 뜬다
- 인터넷이 없거나 이 주소를 못 읽으면 **아무 일도 없었던 것처럼 넘어간다**
  (알림 하나 때문에 도구가 안 돌면 그게 더 나쁘다)
- 쓰는 쪽이 `config.txt` 에서 `VERSION_CHECK_URL` 줄을 지우면 확인 자체를 안 한다

**정말로 쓰지 못하게 막아야 한다면 전산망 API 키를 새로 발급받는다** — 코드로 할 일이 아니다.

## ⚠ 이 저장소는 공개다

`raw.githubusercontent.com` 을 토큰 없이 읽으려면 공개여야 한다.
**그러니 여기에 비밀을 적지 않는다** — API 키도, 사람 이름도, 주소도.
위 세 칸 말고는 아무것도 넣을 이유가 없다.
