# 가상 작업실 아바타 — 이미지 생성 프롬프트 팩

차분한 한국인 여성 디자이너 아바타 / 스타일라이즈드 3D 렌더 / 포트폴리오용 컷아웃 에셋.
아래 프롬프트를 Midjourney · DALL·E(ChatGPT) · Adobe Firefly 등에 붙여 사용하세요.

---

## ★ Midjourney 전용 — 레퍼런스 이미지(검은머리 36번) + 프롬프트 결합

`images/ChatGPT Image …12_14_36.png` (검정 자켓·아이보리 와이드팬츠·흰 스니커즈·태블릿, 검은 긴머리 풀바디)를 **캐릭터 레퍼런스**로 고정하고, 표정·포즈만 바꿔 4가지 상태를 뽑는 방식입니다.

### 진행 방법 (Midjourney 웹 또는 Discord)
1. 먼저 그 이미지를 Midjourney에 업로드해 **이미지 URL**을 얻습니다.
   - Discord: 채팅창에 이미지를 끌어다 놓고 보낸 뒤, 이미지 클릭 → "링크 복사".
   - 웹(midjourney.com): 업로드 후 이미지의 주소를 복사.
2. 아래 프롬프트의 `[IMG]` 자리에 그 URL을 붙여넣습니다.
3. `--cref [IMG] --cw 88` 로 얼굴·헤어·의상을 동일하게 유지한 채 포즈 문장만 바꿉니다.
   - `--cw` (character weight): 90~100이면 의상까지 거의 똑같이, 60~80이면 얼굴 위주로 유지하고 포즈 변화 폭이 커집니다.

### 공통 BASE (이 한 줄을 그대로 쓰고, 끝의 [포즈]만 교체)

> stylized 3D chibi designer doll, calm Korean woman, long straight black hair with soft side-parted bangs, large gentle dark eyes, minimal black oversized blazer over ivory top, ivory high-waist wide-leg trousers with thin belt, clean white chunky sneakers, holding one small slim digital tablet, matte soft-plastic 3D render, smooth clean studio lighting, soft white and silver palette with subtle pale lavender, pale pink and sky blue accents, full body, slight three-quarter view, generous padding, plain white studio background, portfolio character asset, high detail --ar 3:4 --style raw --cref [IMG] --cw 88 --no brown hair, blonde hair, headphones, coffee cup, camera, flowers, tote bag, jewelry, extra accessories, school uniform, busy background, text, watermark, extra characters

### 상태별 (BASE 끝에 아래 [포즈] 문장만 추가/교체)

- **avatar-idle** — `, standing calmly in a relaxed neutral pose, one hand holding the tablet at her side, soft forward gaze`
- **avatar-guide** — `, gently holding up the transparent tablet with both hands as if presenting a folder, attentive welcoming expression`
- **avatar-loading** — `, small calm waiting pose, head tilted slightly, soft half-closed eyes, thoughtful patient mood, tablet held loosely`
- **avatar-contact** — `, relaxed approachable pose beside a small floating chat messenger window UI, warm friendly half-smile looking at the viewer`

### 크로마키(누끼용) 버전이 필요하면
BASE의 `plain white studio background` 를 아래로 교체:
> on a perfectly flat solid #00ff00 green screen, one uniform color, no shadow, no floor, no reflection, no gradient, even flat lighting, do not use green anywhere on the subject

→ `--no` 목록에 `cast shadow, floor, reflection, green tint on subject` 추가.

> 팁: 4장 모두 **같은 `--cref` 이미지와 같은 `--cw` 값**으로 뽑아야 캐릭터가 흔들리지 않습니다. 마음에 드는 idle이 나오면, 그 결과를 다시 `--cref` 로 써서 나머지 3장을 뽑으면 더 일관돼요.

---

## 0. 사용 순서 (중요)

1. 먼저 **idle(기본)** 프롬프트로 마음에 드는 캐릭터를 1장 확정합니다.
2. 그 이미지를 **캐릭터 레퍼런스**로 고정한 뒤(아래 도구별 방법 참고), 표정·포즈만 바꿔 guide / loading / contact 3장을 생성합니다.
   → 이렇게 해야 4장의 얼굴·헤어·의상이 동일하게 유지됩니다.
3. 배경을 깔끔히 지우고(누끼) `assets/` 폴더에 아래 파일명으로 저장합니다.
   - `avatar-idle.webp`
   - `avatar-guide.webp`
   - `avatar-loading.webp`
   - `avatar-contact.webp`

---

## 1. MASTER BASE PROMPT (영문, 공통)

> Stylized 3D character render of a calm Korean female designer avatar, refined chibi-inspired proportions but mature enough for a design portfolio (not childish). Long black hair with soft natural volume, clean side-parted bangs, gentle thoughtful expression, soft large eyes. Outfit: minimal black oversized zip-up jacket, ivory inner top, ivory wide pants, clean white chunky sneakers — modern designer look. Very minimal accessories, no jewelry, no clutter. Soft matte plastic texture with subtle glass and silver chrome accents, clean soft studio lighting. Color palette: soft white, silver, pale lavender, pale pink, sky blue. Mood: calm, polished, warm, quiet early-adopter, soft retro-digital. Full-body, standing, slight three-quarter view, generous padding around the character, easy to cut out. Plain light gray studio background. High quality, portfolio-ready character asset.

**NEGATIVE (피해야 할 요소):**

> brown hair, blonde hair, overly childish baby style, too many accessories, jewelry, charms, keychains, coffee cup, camera, headphones, flowers, fantasy costume, animal hood, idol costume, school uniform, busy background, neon cyberpunk, dark gothic, text, watermark, signature, extra characters, low quality, blurry

---

## 2. 상태별 프롬프트 (BASE + 아래 한 줄만 추가/교체)

### avatar-idle (기본)
> ...standing quietly in a relaxed neutral pose, arms naturally at her sides, calm soft gaze looking slightly forward, holding one small transparent glass tablet lightly in one hand.

### avatar-guide (안내)
> ...holding up a small transparent glass tablet with both hands as if presenting or explaining, gentle attentive expression, one hand gesturing softly toward the viewer, welcoming guide pose.

### avatar-loading (로딩 대기)
> ...in a calm waiting pose, head tilted slightly, soft patient expression with eyes gently half-closed, one hand near her chin, the transparent tablet held loosely, quiet "please wait a moment" mood.

### avatar-contact (메신저 옆)
> ...seated or leaning pose beside a soft glowing chat/messenger window UI element, warm friendly half-smile, looking toward the viewer as if replying to a message, transparent tablet showing a small speech-bubble icon.

---

## 2-B. 크로마키(녹색배경) 버전 — 누끼 최적화 ★추천

배경을 단색 그린으로 두면 자동 누끼가 가장 깔끔합니다. 위 BASE 프롬프트에서 **배경/조명 부분만** 아래 문장으로 교체하세요. (상태별 포즈 문장은 그대로 추가)

> ...isolated on a perfectly flat solid chroma-key green background, pure #00ff00 green screen, one uniform color with absolutely no shadows, no gradients, no texture, no reflections, no floor plane, no lighting variation. Subject fully separated from the background with crisp clean edges and generous empty padding all around. Even flat lighting on the character only. Do NOT use any green (#00ff00) color anywhere on the subject's hair, skin, outfit or accessories.

**이 버전 전용 NEGATIVE (위 공통 네거티브에 더해서):**

> cast shadow, contact shadow, drop shadow, reflection, floor, ground plane, background gradient, vignette, green tint on subject, green clothing, green reflection on skin, text, watermark, logo

**도구별 팁**
- Midjourney: `--no shadow, floor, gradient, reflection` 추가, `--ar 3:4 --style raw`.
- DALL·E/ChatGPT: "solid #00ff00 green screen background, no shadow on the floor, full body with padding" 강조.
- ⚠️ 의상이 검정/아이보리라 그린과 충돌이 없어 누끼가 잘 됩니다. 단, 캐릭터에 초록 반사가 끼면 누끼 시 가장자리가 비치니 NEGATIVE로 꼭 차단하세요.

**누끼 방법**: remove.bg / Photoroom 자동, 또는 Photoshop "색상 범위 → #00ff00 선택 후 삭제" → 가장자리 그린 spill 제거(레이어 > 매팅 > 가장자리 제거).

---

## 3. 도구별 설정 팁

### Midjourney (v6 이상 권장)
- 프롬프트 끝에 파라미터 추가: `--ar 3:4 --style raw --q 2`
- 캐릭터 일관성: idle 이미지를 올린 뒤 그 URL을 `--cref <이미지URL> --cw 80` 으로 고정 → 표정/포즈만 바꿔 나머지 3장 생성.
- 누끼: 배경을 흰색/연회색으로 두면 후처리(누끼)가 쉬움. `--no background, scene`.

### DALL·E / ChatGPT (GPT-4o 이미지)
- BASE + 상태 문장을 그대로 붙여넣기. "Plain light gray background, full body, lots of empty padding around the character" 를 꼭 유지.
- 일관성: 첫 이미지를 첨부하고 "Keep the exact same character, face, hair and outfit. Only change the pose to: ..." 라고 지시.

### Adobe Firefly
- Content type: **Art** 또는 **3D**, Style 강도 중간.
- "Reference image"에 idle 결과를 넣고 Structure/Style 참조로 4장 통일.

---

## 4. 내보내기 & 포트폴리오 적용

1. 4장 모두 **배경 투명 PNG**로 누끼 → WebP로 변환(권장 600×740px 내외, 세로 비율).
   - 무료 누끼: remove.bg / Photoroom / Photoshop "피사체 선택".
2. 파일명을 정확히 `avatar-idle.webp` 등으로 저장.
3. `JEONG-YOUNG-SIM/assets/` 폴더에 넣으면 끝. 코드 수정 없이 자동 반영됩니다.
   (파일이 없을 동안에는 CSS 임시 캐릭터가 보입니다.)

> 팁: 4장의 캔버스 크기·캐릭터 위치를 동일하게 맞추면, 상태가 바뀔 때 캐릭터가 들썩이지 않고 자연스럽게 표정만 바뀌어 보입니다.
