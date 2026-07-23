# 윈도우 11에서 사라진 작업표시줄 데스크밴드, WinUI·WPF로 다시 만들기

2026년 7월 28일 **Dot4 밋업 with 마이크로소프트 코리아** 발표자료 공개본입니다.

> `index.html`을 브라우저로 열면 슬라이드가 그대로 재생됩니다. 방향키·스페이스바로 넘기고, 하단 작업표시줄의 챕터 아이콘으로 원하는 장으로 바로 이동할 수 있습니다.

## 발표 개요

Windows 11이 작업표시줄을 XAML 기반으로 새로 만들면서, Windows 95부터 있던 **데스크밴드(작업표시줄 도구 모음)** API가 통째로 사라졌습니다. 공식 대체재는 없지만, 미디어 컨트롤·시스템 모니터·사용량 표시기처럼 "항상 보이는 작은 자리"에 대한 수요는 여전합니다.

이 발표는 `SetParent` 하나로 시작해 NuGet 패키지 한 줄이면 되는 라이브러리 **Deskband11Lib**를 만들고, 그걸로 실제 앱을 스토어에까지 출시한 개발기입니다.

## 다루는 내용

| # | 챕터 | 핵심 |
|---|------|------|
| 01 | 사라진 데스크밴드 | Windows 11이 없앤 것, 그런데 수요는 여전 |
| 02 | 알고 보니 그냥 창이었다 | zadjii/Deskband11에서 얻은 아이디어 — 투명 창을 작업표시줄의 자식으로 입양 |
| 03 | 작업표시줄에 창 붙이기 | Win32 창 수술 + UI Automation으로 빈 공간 측정 + 정렬 감지 |
| 04 | 라이브러리로 만들기 | Core/Facade 설계, Explorer 재시작 복구, 멀티 인스턴스 슬롯 조율, 애니메이션 |
| 05 | 요즘 .NET으로 Win32 다루기 | CsWin32 소스 생성 P/Invoke, 소스 생성 COM, NativeAOT |
| 06 | PoC에서 스토어까지 | BarPlay·PinStats·CLI Account Switcher 실제 이식 사례 + 라이브 데모 |
| 07 | 한계와 배운 점 | 문서화되지 않은 영역에서의 설계 전략, Q&A |

## 관련 프로젝트

- **Deskband11Lib** — 오늘 소개하는 작업표시줄 호스팅 라이브러리 · [GitHub](https://github.com/airtaxi/Deskband11Lib) (MIT) · NuGet: `Deskband11Lib.WinUI`, `Deskband11Lib.Wpf`
- **BarPlay** — 미디어 위젯, 라이브러리 검증용 PoC에서 Microsoft Store까지 출시
- **PinStats** — 시스템 모니터, 기존 앱에 위젯 기능 이식
- **CLI Account Switcher** — AI CLI 계정·사용량 관리, 마찬가지로 위젯 이식

## 발표자

**이호원 (Howon Lee)** · airtaxi · .NET 데스크톱 개발자

Windows를 좋아해서 C#과 .NET을 시작했고, 지금은 WinUI·Uno Platform으로 Windows 앱을 만듭니다. 오픈소스 Windows 앱을 15개 넘게 공개했습니다 — [github.com/airtaxi](https://github.com/airtaxi)

## 라이선스

MIT License. 발표 시 인용한 타인 프로젝트(zadjii/Deskband11 등)의 자료는 각각의 라이선스를 따릅니다.