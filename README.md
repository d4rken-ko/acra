||현재 상태|
|---|---|
|빌드|[ ![테스트](https://github.com/ACRA/acra/workflows/test/badge.svg?branch=master) ](https://github.com/ACRA/acra/actions?query=workflow%3Atest)|
|Maven Central|[![Maven Central](https://img.shields.io/maven-central/v/ch.acra/acra-core.svg)](https://search.maven.org/#search%7Cga%7C1%7Cg%3A%22ch.acra%22)|
|안드로이드 버전|![최소 버전](https://img.shields.io/badge/dynamic/json?label=Android%20Min%20Version&query=version&url=https%3A%2F%2Ffaendir.com%2Fandroid%2Facra.php%3Fversion%3Dandroid-min) ![대상 버전](https://img.shields.io/badge/dynamic/json?label=Android%20Target%20Version&query=version&url=https%3A%2F%2Ffaendir.com%2Fandroid%2Facra.php%3Fversion%3Dandroid-target)|
|라이선스|![라이선스](https://img.shields.io/github/license/ACRA/acra.svg)|
| 통계|[![AppBrain 통계](https://www.appbrain.com/stats/libraries/shield/acra.svg)](https://www.appbrain.com/stats/libraries/details/acra/acra)|

ACRA란?
===============

ACRA는 Android 개발자가 애플리케이션에 충돌 보고를 쉽게 통합할 수 있는 오픈 소스 라이브러리입니다. 사용자 정의 보고, 여러 발신자 지원, 유연한 데이터 수집 옵션을 포함한 포괄적인 기능 세트를 제공하여 개발자가 앱의 문제를 빠르게 식별하고 진단할 수 있습니다.

ACRA는 2020년 6월 현재 Google Play의 모든 앱 중 1.57%([AppBrain/통계 참조](https://www.appbrain.com/stats/libraries/details/acra/acra))에서 사용됩니다. 이는 **13,000개가 넘는 앱**과 ACRA를 포함한 **50억 건이 넘는 다운로드**입니다.

Android 앱의 충돌 보고 기능은 Android 2.2(FroYo)부터 기본 제공되지만 공식 Android Market(제한된 데이터 포함)을 통해서만 사용할 수 있습니다. ACRA는 Android 개발자에게 큰 도움이 됩니다.

* [개발자가 구성 가능한 사용자 상호 작용](https://www.acra.ch/docs/Interactions): 무음 보고, 토스트 알림, 상태 표시줄 알림 또는 대화 상자
* 공식 지원 라이브러리에서 지원하는 모든 버전의 Android에서 사용 가능
* Android Market 개발자 콘솔 오류 보고서에 표시된 것보다 앱을 실행하는 기기에 대한 [자세한 충돌 보고서](https://www.acra.ch/javadoc/latest/org/acra/ReportField.html)가 더 많습니다.
* 보고서에 [자신만의 변수 콘텐츠나 디버그 추적을 추가](https://www.acra.ch/docs/AdvancedUsage#adding-your-own-custom-variables-or-traces-in-crash-reports-breadcrumbs)할 수 있습니다.
* [애플리케이션이 충돌하지 않더라도 오류 보고서를 보낼 수 있습니다](https://www.acra.ch/docs/AdvancedUsage#sending-reports-for-caught-exceptions-or-for-unexpected-application-state-without-any-exception)
* Google Play를 통해 제공되지 않더라도 모든 애플리케이션에서 작동합니다 => Google Play를 사용할 수 없는 기기/지역, 베타 릴리스 또는 엔터프라이즈 비공개 앱에 적합합니다.
* if 네트워크 범위가 없으며, 보고서는 보관되어 나중에 애플리케이션을 다시 시작할 때 전송됩니다.
* [자체 호스팅 보고서 수신자 스크립트](https://www.acra.ch/docs/Senders)와 함께 사용할 수 있습니다.

ACRA의 알림 시스템은 깔끔합니다. 충돌이 발생하면 애플리케이션은 기존 시스템의 충돌 알림이나 보고 기능 위에 사용자 알림을 추가하지 않습니다. 기본적으로 "강제 종료" 대화 상자는 더 이상 표시되지 않으며, 이를 활성화하려면 `alsoReportToAndroidFramework`를 `true`로 설정합니다.

사용자에게는 오류가 한 번만 알려지며, 알림/대화 상자에서 고유한 텍스트를 정의하여 애플리케이션의 인식된 품질을 향상시킬 수 있습니다.

[문제 추적기](https://github.com/ACRA/acra/issues)에서 결함/개선 요청을 주저하지 말고 열어주세요.

사용 방법
=====
저희 [웹사이트](https://www.acra.ch/docs/Setup)는 초기 설정에 대한 단계별 가이드와 고급 사용 정보를 다룹니다.

최신 버전
==============================================

최신 버전과 전체 변경 로그는 [릴리스 페이지](https://github.com/ACRA/acra/releases)에서 확인하세요.

4.x에서 마이그레이션하는 경우 위키의 [마이그레이션 가이드](https://github.com/ACRA/acra/wiki/Migrating)를 참조하세요.

백엔드
========

[Acrarium](https://github.com/F43nd1r/Acrarium)은 보고서 저장 및 분석을 위한 공식 백엔드입니다. Acrarium은 여전히 활발하게 개발 중입니다.

[Acralyzer](https://github.com/ACRA/acralyzer)는 그 전에 공식 백엔드였습니다. CouchDB에서 실행되며, 무료 호스팅 솔루션이 있습니다. 기능은 완벽하지만 현재 유지 관리되지 않습니다. 이 프로젝트를 시작하는 모든 사람을 환영합니다.

[많은 다른 솔루션](https://www.acra.ch/docs/Backends)이 커뮤니티에서 제공되었으므로 가장 마음에 드는 솔루션을 확인하세요.
