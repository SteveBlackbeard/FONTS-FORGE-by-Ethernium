# 🛠️ FONTS FORGE by Ethernium

![Ethernium 견본 시트](../ethernium_sheet_hq.png)

간단한 손으로 그린 또는 그리드 기반 래스터 견본 시트(PNG)에서 **맞춤형 벡터 폰트를 디자인, 컴파일 및 시각화하는** 전문적이고 최첨단의 툴킷입니다.

포렌식 수준의 정밀도와 사이버펑크 미학으로 제작되었습니다.

---

## ✨ 기능

- **범용 래스터-벡터 변환 파이프라인**: 그리드 기반 견본을 완벽한 문자 바운딩 박스로 자동 분할하고, 글리프 윤곽을 추출하여 벡터 형식으로 변환합니다.
- **기하학적 스내핑 및 스무딩**: 선명한 디테일을 유지하면서 계단 현상을 제거하는 구성 가능한 각도 스내핑(45° / 90°) 및 형태학적 엣지 필터.
- **베지어 곡선 피팅**: 전문가 수준의 곡선을 위한 편향각 분석을 사용한 자동 2차/3차 베지어 분류.
- **이중 레이어 대칭 엔진**: 벡터 및 픽셀 수준 모두에서 수학적으로 완벽한 대칭을 위해 윤곽을 좌우로 미러링합니다.
- **포렌식 워터마킹**: 저작권 증명을 위한 LSB 기반 스테가노그래픽 좌표 임베딩.
- **전문 OpenType 테이블**: 견고한 OS/2 수직 메트릭, `gasp` 화면 렌더링 힌팅, 저작권 레코드 및 레거시 커닝 맵.
- **다중 형식 출력**: 단일 빌드로 `.ttf`, `.woff`, `.woff2`를 생성합니다.

---

## 🌐 인터랙티브 웹 도구

| 도구 | 설명 |
|------|-------------|
| `preview_font.html` | 클립보드 복사, 워터폴 견본(12px–72px), CSS 임베딩 코드를 포함한 완전한 문자 그리드 |
| `ascii_generator.html` | 다중 렌더링 모드를 지원하는 실시간 Canvas 기반 ASCII 아트 생성기 |
| `presentation_generator.html` | 쇼케이스 포스터용 프리미엄 프레젠테이션 카드 렌더러 |
| `unicode_converter.html` | 룬 문자 및 특수 기호 Unicode 맵과 변환기 |

---

## 🚀 4단계로 맞춤 폰트 만들기

### 1단계: 견본 시트 그리기
하나의 PNG 이미지에 폰트 글리프를 그리거나 구성합니다. 문자를 행별로 왼쪽에서 오른쪽으로 배열합니다.

### 2단계: 프로젝트 구성
`configs/template.json`을 `configs/my_font.json`으로 복사하고 다음을 정의합니다:
- `"sheet"`: PNG 파일명
- `"font"`: 저작권, 패밀리명, 스타일명
- `"rows"`: Y 좌표와 각 행의 정렬된 문자 목록

> 💡 **자동 보정**: `python tools/calibrate_sheet.py my_sheet.png`을 실행하여 Y 경계를 자동으로 감지합니다.

### 3단계: 컴파일
```bash
pip install -r requirements.txt
python -m font_forge configs/my_font.json
```

### 4단계: 미리보기 및 배포
브라우저에서 `preview_font.html`을 열어 글리프 그리드를 검사하고, 크기를 테스트하고, 임베딩 코드를 가져옵니다.

---

## 🔬 개발자 도구

| 스크립트 | 용도 |
|--------|--------|
| `tools/calibrate_sheet.py` | 자동 Y 경계 스캔 및 밴드 제안 |
| `tools/debug_rows.py` | 좌표 슬라이스의 시각적 검증 오버레이 |
| `tools/audit_font.py` | 컴파일된 수직 경계 및 글리프 범위의 무결성 검증 |
| `tools/validate_font.py` | OpenType 사양 감사기 (통과/경고/실패 보고서) |
| `tools/font_to_ascii.py` | 텍스트를 고해상도 터미널 ASCII 배너로 변환 |
| `tools/export_atlas.py` | 컴파일된 TTF에서 시각적 글리프 아틀라스 생성 |

---

## 📦 요구 사항

```bash
pip install -r requirements.txt
```

**Python 3.8+** 및 `opencv-python`, `numpy`, `fonttools`, `Pillow`가 필요합니다.

---

## 📄 라이선스

이 툴킷은 오픈 소스이며 [MIT 라이선스](../LICENSE.txt) 하에 이용 가능합니다.

---

<p align="center">
  <b>FONTS FORGE</b> — <a href="https://github.com/SteveBlackbeard">Ethernium</a>이 단조
</p>
