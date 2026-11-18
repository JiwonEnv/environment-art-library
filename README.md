# Environment Art Library

게임 환경 아트용 재질, 프롭, 텍스처 원본 모음입니다.
Substance 3D Designer와 Substance 3D Painter로 만든 작업 파일과 내보낸 텍스처를 에셋 단위로 정리합니다.

## 재질 (Materials)

| 미리보기 | 이름 | 설명 | 핵심 노드 |
|---|---|---|---|
| <img src="materials/flagstone_floor_a/preview.png" width="160"> | [`flagstone_floor_a`](materials/flagstone_floor_a) | 스타일라이즈드 판석 바닥. 불규칙한 다각형 돌, 줄눈 흙·자갈, 젖은 얼룩 | Voronoi, Flood Fill, Bevel, Slope Blur, Curvature |
| <img src="materials/stone_brick_wall_a/preview.png" width="160"> | [`stone_brick_wall_a`](materials/stone_brick_wall_a) | 스타일라이즈드 돌벽돌 벽. 모서리 깎임, 금 간 벽돌, 줄눈 자갈 | Tile Generator, Flood Fill, Bevel, Slope Blur, Directional Warp |
| (준비 중) | [`rope_a`](materials/rope_a) | 밧줄 재질 (작업 중) | |

## 폴더 구조

```
environment-art-library/
├─ materials/        타일링 재질 (에셋마다 폴더 하나)
│   └─ <이름>/
│       ├─ <이름>.sbs     Substance Designer 원본
│       ├─ textures/      내보낸 맵 (BaseColor, Normal, Roughness ...)
│       └─ preview.png    미리보기
├─ props/            프롭 (메시 + Painter 프로젝트 + 텍스처)
│   └─ <이름>/
│       ├─ <이름>.fbx
│       ├─ <이름>.spp
│       ├─ textures/
│       └─ preview.png
└─ textures/         데칼, 알파, 브러시 같은 단독 텍스처
```

## 이름 규칙

- 영어 소문자 + 밑줄: `재질종류_형태_변형` (예: `flagstone_floor_a`, `stone_brick_wall_a`)
- 폴더 이름 = 원본 파일 이름 = Designer 그래프 이름

## 작업 환경

- Substance 3D Designer 16.0
- 출력 맵: Base color, Normal (DirectX), Height, Roughness, Metallic, AO, Curvature
- 높이 계열은 16비트로 작업

## 참고

- `.sbs`는 XML 텍스트라 일반 Git으로 관리합니다.
- 이미지, `.sbsar`, `.spp`, `.fbx` 등 큰 파일은 Git LFS로 관리합니다. 내려받을 때 `git lfs install` 후 clone 하세요.
- `.sbs`는 Designer 기본 라이브러리(`sbs://`)만 참조하므로 따로 받을 파일 없이 바로 열 수 있습니다.
