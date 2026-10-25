# 회전 용기 수면 높이차 계산기

액체가 용기와 함께 강체 회전할 때 두 반지름 위치 사이의 부호 있는 자유수면 높이차를 계산합니다.

- ID: E138
- App: https://nanalab.kr/eng-rotating-free-surface/
- Repository: https://github.com/NaNaCompany/eng-rotating-free-surface
- Formula: Δz = z(r₂)−z(r₁) = ω²(r₂²−r₁²)/(2g)

## Model and data

수직축을 중심으로 일정한 각속도로 강체 회전하며 중력과 자유수면 압력이 일정합니다. 두 위치에 실제 액체가 있어야 하고 넘침이나 바닥 노출이 없어야 합니다. 결과는 z(r₂)−z(r₁)이므로 두 번째 위치가 축에 가까우면 음수입니다. 정지 시 수심이나 필요한 액체량은 계산하지 않습니다.

Inputs normalize to SI. Repeated-input models support adding/removing actual input rows. Calculations, finite-number checks and physical-domain checks run locally; no external property database or solver API is used.

## Validation

Run node --test tests/*.test.mjs and python scripts/build-locales.py --check. tests/reference.json contains independently computed high-precision default and boundary references. The source notices distinguish original MIT work from citation-only external references.

## Static languages

Korean (existing root), English (`en/`), Spanish (`es/`), Simplified Chinese (`zh/`), Japanese (`ja/`) and German (`de/`). Each page has its own canonical URL, reciprocal hreflang, localized metadata, interface, validation messages and preview image. The language links work without JavaScript. Calculation code is shared and no runtime translation API is used.

Edit `localization/*.json` for text, `src/template.html` for the shared page, and run `python scripts/build-locales.py`. Run `python scripts/build-locales.py --check` and `npm test` before publishing. Decimal commas are accepted in Spanish and German; thousands separators are not supported.
