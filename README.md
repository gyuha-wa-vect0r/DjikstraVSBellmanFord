# 최단 거리 도출 성능 분석: Dijkstra Algorithm과 Bellman-Ford Algorithm 비교

## 📌 프로젝트 개요
이 프로젝트는 Python을 활용해 Dijkstra Algorithm과 Bellman-Ford Algorithm을 구현하고, OpenStreetMap 데이터를 기반으로 충청북도 청주시의 도로망에서 두 알고리즘의 성능을 비교 분석한 결과를 담고 있습니다.  
주요 분석 포인트는 다음과 같습니다:

- 최단 경로의 정확성  
- 실행 시간  
- 메모리 사용량  
- 시각화를 통한 결과 비교  
- 상용 지도 서비스와의 비교

## 🔍 주요 목표
1. **라우팅 알고리즘 구현 및 심화 학습**:  
   - Dijkstra 및 Bellman-Ford 알고리즘의 구현과 성능 차이를 분석.  
   - 알고리즘의 시간 복잡도와 메모리 효율성을 검증.

2. **OpenStreetMap 데이터를 활용한 실질적 테스트**:  
   - 청주시 도로망 데이터를 활용해 알고리즘의 실제 동작 확인.

3. **결과 시각화 및 비교 분석**:  
   - 각 알고리즘의 경로 결과를 시각적으로 표현하고, 상용 지도 서비스와 비교.

## 💻 개발 환경
- 운영 체제: Ubuntu 24.04 (Windows 11 WSL2)  
- Python 버전: 3.9.20

### 사용된 주요 라이브러리
- **osmnx**: OpenStreetMap 데이터를 활용한 네트워크 그래프 생성  
- **heapq**: 다익스트라 알고리즘에서 우선순위 큐 구현  
- **tracemalloc**: 메모리 사용량 추적  
- **time**: 알고리즘 실행 시간 측정

## 📂 프로젝트 구조
```bash
.
├── FINAL.py             # 메인 Python 코드
├── README.md            # 프로젝트 설명서
├── requirements.txt     # 필수 라이브러리 설치 파일
├── results/
│   ├── graph.png        # 생성된 도로망 그래프 시각화
│   ├── dijkstra_path.png# 다익스트라 경로 시각화
│   └── bellman_path.png # 벨만-포드 경로 시각화
└── data/
    ├── nodes.gpkg       # 도로망 노드 데이터
    └── edges.gpkg       # 도로망 엣지 데이터
