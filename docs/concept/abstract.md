# In-Gage — Concept Abstract

> Stage: **Composition** (구성 → 구체 → Deploy) · Target: production handoff in ~3 months
> Status: draft v0.1 · 2026-10-13

---

## 1. Abstract

**In-Gage: A Prepared-State Architecture for Discreet Personal Safety on iOS**

Personal-safety risk is rarely announced in advance. Commutes, first meetings, travel, and situations involving stalking or coercive control can shift from ordinary to threatening within minutes, often in the physical presence of the person creating the risk. Most mobile safety tools, however, are built around a single visible act: opening an emergency app, pressing an SOS button, or placing a call. In exactly the scenarios where help matters most, that visible act can itself escalate danger, reveal intent to an aggressor, or be physically prevented.

In-Gage reframes the primary user as a *potential victim*: a person who is currently safe, whose risk is situational and unpredictable, and who wants to prepare without appearing to be "in danger." Rather than an emergency-only tool, In-Gage is a prepared-state safety architecture. Users configure their safety plan in advance — trusted contacts, check-in routines, regional emergency resources, and personal activation patterns — so that, under stress, requesting help requires only a familiar, low-visibility interaction.

The system has three layers. First, a **discreet interface layer** offers original, fully functional everyday surfaces — a calculator, notes, planner, weather view, or assistant-style chat — inside a single app, giving plausible deniability under casual observation without imitating any commercial product or brand. Second, a **multi-trigger framework** lets users define covert activation patterns native to each surface: a private numeric sequence, a predefined phrase, a specific note or calendar entry, or a deliberate gesture sequence. Third, every trigger routes into a shared **Safety Engine** that executes a user-defined escalation ladder rather than a fixed "call emergency services" response. Depending on configuration and jurisdiction, the engine may alert trusted contacts with live location, start a check-in countdown, preserve timestamped evidence, or guide the user toward an emergency-service handoff where local infrastructure supports it.

Reliability and restraint are first-class requirements. Triggers are designed to be improbable by accident, staged through a short cancellable grace window, and verifiable through a rehearsal mode. Data is minimized and kept on-device by default. Platform constraints — a fixed app identity on the Home Screen, user-visible privacy indicators, background-execution limits, and the absence of universal silent emergency calling — are treated as design inputs, and every discreet feature is disclosed to the user and to App Review.

In-Gage does not claim to prevent crime or guarantee an emergency response. Its contribution is a design pattern for help-seeking under observation: separating the *expression* of a request for help from its *visible appearance*, so that personal safety remains invisible when unnecessary and immediate when necessary.

*(≈ 410 words)*

---

## 2. One-sentence thesis

In-Gage separates the act of asking for help from its visible appearance, letting potential victims prepare a safety plan before danger occurs and activate it through ordinary-looking interactions that feed a configurable, region-aware Safety Engine.

## 3. Candidate keywords

1. Covert help-seeking
2. Prepared-state safety
3. Discreet interaction design

## 4. Alternative product-category labels

1. Preventive covert safety platform
2. Discreet personal-safety system
3. Multi-trigger safety interface

## 5. Weakest point (critique)

**The concept specifies the trigger far more precisely than the response.** Covert activation is only as valuable as what happens next, yet the response end is the least defined and least controllable part: iOS cannot silently dial emergency services, text-to-emergency coverage varies by country, and trusted contacts may not see or act on an alert in time. Without a defined response guarantee per launch region (who receives the alert, within what time, and what happens if no one acknowledges), In-Gage risks giving users a feeling of protection that is stronger than the protection it delivers.

## 6. Recommendation for App Store defensibility

**Ship a transparent safety app with a documented discreet mode, not a disguised app.**

- Keep one honest, fixed app name and icon. The alias surfaces live *inside* the app and are chosen by the user during onboarding; do not rely on runtime icon or name changes (alternate icons show a system alert and do not change the app's name).
- Make each alias surface genuinely functional (the calculator calculates, notes save), so no screen is a decoy shell.
- Keep triggers off by default and user-configured, and document every trigger and escalation path in App Review notes with a demo video and test account. This answers the "hidden, dormant, or undocumented features" rule instead of colliding with it.
- Cite existing precedents — App Store apps with user-enabled discreet modes for survivors, and calculator-style privacy vaults — to frame the alias layer as an established, accepted safety pattern.

---

## 7. 구성 단계 메모 — 구체 단계로 넘기기 전 확정할 결정

| # | 결정 항목 | 왜 지금 정해야 하나 |
|---|---|---|
| 1 | **위협 모델 등급** — (a) 옆에서 흘끗 보는 수준, (b) 폰을 직접 열어 보는 수준, (c) 기기를 통제하는 강압적 관계 | alias가 어디까지 버텨야 하는지에 따라 UI·알림·데이터 저장 설계가 전부 달라짐. iOS 설정, 앱스토어 구매 내역, 마이크/위치 표시등은 숨길 수 없으므로 (c)는 "완전 은닉" 대신 "의심 최소화"로 범위를 정해야 함 |
| 2 | **출시 지역과 지역별 대응 경로** | 예: 한국은 112 문자신고, 미국은 Text-to-911(지역별 상이). 첫 출시 지역을 1곳으로 좁히고 그 지역의 응답 경로를 끝까지 설계 |
| 3 | **응답 보장 정의** | 알림 수신자, 응답 확인(ack) 방식, 무응답 시 다음 단계와 시간 기준 — 위 Critique의 해결책 |
| 4 | **MVP alias 개수** | 6종 전부가 아니라 1–2종(예: 계산기 + 노트)으로 시작해 트리거 문법과 오작동률을 먼저 검증 |
| 5 | **트리거 문법 & 오작동 KPI** | 2단계(무장 → 확정), 취소 유예 시간, 강요 시 입력하는 duress 코드와 일반 취소 코드의 구분, 목표 오작동률 수치 |
| 6 | **App Review 전략 문서** | 위 Recommendation을 심사 노트 초안으로 미리 작성 — Deploy 단계에서 리젝 리스크를 줄임 |
