# 리웨어스 (ReWearth) - 개발 지침서

> **Claude AI를 위한 안내**
> 이 문서는 프로젝트의 개발 지침서입니다. 새로운 Claude 세션에서 개발을 시작할 때 이 문서를 참조하세요.

---

## 문서 읽기 타이밍 가이드

### 이 문서를 읽어야 하는 경우
1. **새 세션 시작 시**: 프로젝트 개요와 현재 진행 상황 파악
2. **작업 재개 시**: "진행 상황" 섹션만 확인하여 이어서 작업
3. **새로운 화면 개발 시**: 디자인 가이드라인과 컴포넌트 규칙 참조

### 읽지 않아도 되는 경우
- 동일 세션 내에서 연속 작업 중일 때
- 단순 버그 수정이나 작은 수정 작업 시

### 효율적인 읽기 방법
- **전체 파악 필요 시**: 전체 문서 읽기
- **작업 재개 시**: "진행 상황" 섹션 (라인 50~100 근처)만 읽기
- **디자인 참조 시**: "디자인 가이드라인" 섹션만 읽기

---

## 프로젝트 개요

| 항목 | 내용 |
|------|------|
| **프로젝트명** | 리웨어스 (ReWearth) |
| **플랫폼** | Flutter (iOS/Android) |
| **서비스 유형** | 의류 대여 서비스 앱 |
| **GitHub** | https://github.com/TAEHONG-LEE/rewearth |
| **로컬 경로** | C:\rewearth |

---

## 기술 스택

| 영역 | 기술 |
|------|------|
| Frontend | Flutter 3.x |
| State Management | Riverpod (권장) |
| Backend | Firebase |
| 인증 | Firebase Authentication (Phone Auth) |
| 데이터베이스 | Cloud Firestore |
| 스토리지 | Firebase Storage |
| 지도 | Google Maps Flutter |
| 캘린더 | table_calendar 패키지 |
| 이미지 | cached_network_image |
| 폰트 | Pretendard |

---

## 진행 상황

### 현재 단계
**Phase 1 (MVP) - 화면 디자인 단계**

### 완료된 작업
| 날짜 | 작업 내용 | 상태 |
|------|----------|------|
| 2025-11-30 | 프로젝트 초기 설정 (폴더 생성, GitHub 연동) | 완료 |
| 2025-11-30 | CLAUDE.md 지침서 작성 | 완료 |
| 2025-11-30 | Figma 화면 디자인 (7개 완료) | 완료 |

### 진행 중인 작업
| 화면 | 상태 | 비고 |
|------|------|------|
| ProfileSetup | 대기 | 다음 작업 |
| DateSelection | 대기 | 예약 플로우 |
| PickupLocation | 대기 | 예약 플로우 |

### 다음 작업
1. ProfileSetup 화면 디자인
2. DateSelection 화면 디자인
3. 나머지 예약 플로우 화면들

---

## 화면 개발 순서 (MVP)

| 순번 | 화면명 | 설명 | 상태 |
|------|--------|------|------|
| 1 | Splash | 스플래시 화면 | 완료 |
| 2 | Home | 홈 화면 | 완료 |
| 3 | Category | 카테고리 화면 | 완료 |
| 4 | ProductDetail | 상품 상세 | 완료 |
| 5 | LoginPopup | 로그인 유도 팝업 (BottomSheet) | 완료 |
| 6 | PhoneInput | 전화번호 입력 | 완료 |
| 7 | OTPInput | 인증번호 입력 | 완료 |
| 8 | ProfileSetup | 프로필 설정 | 대기 |
| 9 | DateSelection | 날짜 선택 | 대기 |
| 10 | PickupLocation | 픽업 장소 선택 | 대기 |
| 11 | ReservationConfirm | 예약 확인 | 대기 |
| 12 | PaymentGuide | 결제 안내 | 대기 |
| 13 | MyReservations | 내 예약 | 대기 |
| 14 | ReservationDetail | 예약 상세 | 대기 |
| 15 | MyPage | 마이페이지 | 대기 |
| 16 | EditProfile | 프로필 수정 | 대기 |

---

## 디자인 가이드라인

### 컬러 팔레트
| 용도 | 색상명 | HEX | 사용처 |
|------|--------|-----|--------|
| Primary | 블랙 | #000000 | 앱바, 주요 텍스트, 버튼 |
| Background | 화이트 | #FFFFFF | 배경 |
| Accent | 버건디 | #800020 | CTA 버튼, 강조, 뱃지 |
| Surface | 라이트 그레이 | #F5F5F5 | 카드 배경, 구분선 |
| Text Primary | 블랙 | #000000 | 제목, 본문 |
| Text Secondary | 다크 그레이 | #666666 | 부가 설명 |
| Text Tertiary | 미디엄 그레이 | #999999 | 힌트, 비활성 |
| Disabled | 라이트 그레이 | #CCCCCC | 비활성 버튼/텍스트 |
| Error | 레드 | #D32F2F | 에러 메시지 |
| Success | 그린 | #388E3C | 성공, 예약가능 |

### 타이포그래피
| 용도 | 크기 | 굵기 |
|------|------|------|
| H1 (페이지 제목) | 24sp | Bold |
| H2 (섹션 제목) | 20sp | SemiBold |
| H3 (카드 제목) | 16sp | Medium |
| Body1 | 14sp | Regular |
| Body2 | 14sp | Regular |
| Caption | 12sp | Regular |
| Button | 14sp | SemiBold |
| Price | 18sp | Bold |

### 컴포넌트 스타일
| 컴포넌트 | 스타일 |
|----------|--------|
| Primary 버튼 | 버건디 배경, 화이트 텍스트, radius 8dp |
| Secondary 버튼 | 블랙 배경, 화이트 텍스트, radius 8dp |
| Outlined 버튼 | 화이트 배경, 블랙 테두리, 블랙 텍스트 |
| 카드 | 화이트 배경, radius 12dp, 그림자 subtle |
| 입력 필드 | Outlined, radius 8dp, 포커스 시 블랙 테두리 |
| 칩 (선택) | 미선택: 그레이 배경 / 선택: 블랙 배경 + 화이트 텍스트 |
| 하단 탭바 | 화이트 배경, 선택 시 블랙 아이콘 + 버건디 인디케이터 |

---

## Figma MCP 연동 방법

### 연결 순서
1. Figma에서 `Plugins > Talk To Figma MCP` 실행
2. 플러그인에 표시된 채널 ID 확인
3. `mcp__TalkToFigma__join_channel` 도구로 채널 연결
4. `mcp__TalkToFigma__get_document_info`로 문서 구조 확인

### 주요 도구
| 도구 | 용도 |
|------|------|
| `get_document_info` | 문서 전체 구조 확인 |
| `get_selection` | 현재 선택 요소 확인 |
| `read_my_design` | 선택된 디자인 상세 정보 |
| `get_node_info` | 특정 노드 상세 정보 |
| `create_frame` | 프레임 생성 |
| `create_text` | 텍스트 생성 |
| `create_rectangle` | 사각형 생성 |

---

## Flutter 프로젝트 구조 (예정)

```
lib/
├── main.dart
├── app/
│   ├── app.dart
│   └── routes.dart
├── core/
│   ├── constants/
│   │   ├── colors.dart
│   │   ├── text_styles.dart
│   │   └── dimensions.dart
│   ├── theme/
│   │   └── app_theme.dart
│   └── utils/
├── features/
│   ├── splash/
│   ├── home/
│   ├── category/
│   ├── product/
│   ├── auth/
│   ├── reservation/
│   └── profile/
├── shared/
│   ├── widgets/
│   └── models/
└── services/
    ├── firebase/
    └── api/
```

---

## 네이밍 컨벤션

### 파일 네이밍
| 종류 | 규칙 | 예시 |
|------|------|------|
| 화면 | snake_case + _screen | `home_screen.dart` |
| 위젯 | snake_case + _widget | `product_card_widget.dart` |
| 모델 | snake_case + _model | `product_model.dart` |
| 서비스 | snake_case + _service | `auth_service.dart` |
| 컨트롤러 | snake_case + _controller | `home_controller.dart` |

### 변수/함수 네이밍
```dart
// 상수: lowerCamelCase with const
const primaryColor = Color(0xFF000000);
const accentBurgundy = Color(0xFF800020);

// 변수/함수: lowerCamelCase
final productList = <Product>[];
void fetchProducts() {}

// 클래스: PascalCase
class ProductCard extends StatelessWidget {}

// private: _prefix
void _handleTap() {}
```

---

## Flutter 개발 베스트 프랙티스

### State Management 선택 가이드

| 라이브러리 | 적합한 프로젝트 | 특징 |
|------------|----------------|------|
| **Riverpod** (권장) | 중~대규모 앱 | 컴파일 타임 안전성, 유연성, Riverpod 3.0 (2024.10) |
| Provider | 소~중규모 앱 | 공식 지원, 간단함 |
| BLoC | 엔터프라이즈 앱 | 엄격한 아키텍처, 테스트 용이 |
| Cubit | 중규모 앱 | BLoC보다 간단, 구조화된 상태관리 |

> 이 프로젝트는 **Riverpod**을 사용합니다.

### 프로젝트 구조 원칙

#### Feature-First 구조 (권장)
```dart
// 파일 타입이 아닌 기능별로 그룹화
lib/
├── features/
│   ├── home/
│   │   ├── data/           # 데이터 레이어 (repository, datasource)
│   │   ├── domain/         # 비즈니스 로직 (model, usecase)
│   │   ├── presentation/   # UI 레이어 (screen, widget, controller)
│   │   └── home.dart       # barrel file
│   ├── product/
│   └── auth/
├── shared/                 # 공유 컴포넌트
└── core/                   # 핵심 유틸리티
```

#### 장점
- 기능별 독립성 유지
- 변경 영향 범위 최소화
- 새 기능 추가 용이
- 팀 협업 효율적

### 성능 최적화 가이드

#### Widget 최적화
```dart
// 1. const 생성자 적극 활용
const SizedBox(height: 16);
const Text('정적 텍스트');

// 2. 복잡한 위젯 분리
// Bad: 하나의 큰 build 메서드
// Good: 작은 위젯으로 분리

// 3. build 메서드는 가볍게
// - 무거운 연산은 initState나 별도 메서드에서
// - 비동기 작업은 FutureBuilder/StreamBuilder 사용
```

#### 이미지 최적화
```dart
// cached_network_image 사용
CachedNetworkImage(
  imageUrl: imageUrl,
  placeholder: (context, url) => CircularProgressIndicator(),
  errorWidget: (context, url, error) => Icon(Icons.error),
);
```

#### 리스트 최적화
```dart
// ListView.builder 사용 (lazy loading)
ListView.builder(
  itemCount: items.length,
  itemBuilder: (context, index) => ProductCard(item: items[index]),
);

// 무한 스크롤 시 pagination 적용
```

### 코드 품질 가이드

#### Lint 규칙 (analysis_options.yaml)
```yaml
include: package:flutter_lints/flutter.yaml

linter:
  rules:
    - prefer_const_constructors
    - prefer_const_declarations
    - avoid_print
    - prefer_single_quotes
    - sort_constructors_first
```

#### 폴더별 Barrel File
```dart
// features/home/home.dart
export 'presentation/home_screen.dart';
export 'presentation/widgets/banner_slider.dart';
export 'domain/models/banner_model.dart';
```

### Riverpod 패턴 가이드

#### Provider 정의
```dart
// 1. StateNotifierProvider (상태 변경이 필요한 경우)
final cartProvider = StateNotifierProvider<CartNotifier, CartState>((ref) {
  return CartNotifier();
});

// 2. FutureProvider (비동기 데이터)
final productsProvider = FutureProvider<List<Product>>((ref) async {
  return ref.read(productRepository).getProducts();
});

// 3. Provider (단순 값 또는 의존성)
final productRepository = Provider<ProductRepository>((ref) {
  return ProductRepository(ref.read(firestoreProvider));
});
```

#### Consumer 사용
```dart
// ConsumerWidget 사용
class HomeScreen extends ConsumerWidget {
  @override
  Widget build(BuildContext context, WidgetRef ref) {
    final products = ref.watch(productsProvider);
    return products.when(
      data: (data) => ProductGrid(products: data),
      loading: () => LoadingIndicator(),
      error: (e, st) => ErrorWidget(error: e),
    );
  }
}
```

### Firebase 통합 패턴

#### Repository 패턴
```dart
// domain/repositories/product_repository.dart
abstract class ProductRepository {
  Future<List<Product>> getProducts();
  Future<Product> getProductById(String id);
  Stream<List<Product>> watchProducts();
}

// data/repositories/product_repository_impl.dart
class ProductRepositoryImpl implements ProductRepository {
  final FirebaseFirestore _firestore;

  @override
  Future<List<Product>> getProducts() async {
    final snapshot = await _firestore.collection('products').get();
    return snapshot.docs.map((doc) => Product.fromFirestore(doc)).toList();
  }
}
```

#### Phone Auth 플로우
```dart
// 1. 전화번호 인증 요청
await FirebaseAuth.instance.verifyPhoneNumber(
  phoneNumber: '+82$phoneNumber',
  verificationCompleted: (credential) async {
    await FirebaseAuth.instance.signInWithCredential(credential);
  },
  verificationFailed: (e) => showError(e.message),
  codeSent: (verificationId, resendToken) {
    // OTP 입력 화면으로 이동
  },
  codeAutoRetrievalTimeout: (verificationId) {},
);

// 2. OTP 코드 확인
final credential = PhoneAuthProvider.credential(
  verificationId: verificationId,
  smsCode: otpCode,
);
await FirebaseAuth.instance.signInWithCredential(credential);
```

### 필수 패키지 목록

```yaml
dependencies:
  flutter:
    sdk: flutter

  # State Management
  flutter_riverpod: ^2.4.9

  # Firebase
  firebase_core: ^2.24.2
  firebase_auth: ^4.16.0
  cloud_firestore: ^4.14.0
  firebase_storage: ^11.6.0

  # UI
  cached_network_image: ^3.3.1
  flutter_svg: ^2.0.9
  shimmer: ^3.0.0

  # Navigation
  go_router: ^13.1.0

  # Utils
  intl: ^0.19.0
  equatable: ^2.0.5

  # Maps & Calendar
  google_maps_flutter: ^2.5.3
  table_calendar: ^3.0.9

dev_dependencies:
  flutter_test:
    sdk: flutter
  flutter_lints: ^3.0.1
  build_runner: ^2.4.8
```

---

## 변경 이력

| 날짜 | 변경 내용 | 섹션 |
|------|----------|------|
| 2025-11-30 | 초기 문서 작성 | 전체 |
| 2025-11-30 | Flutter 베스트 프랙티스 추가 | Flutter 개발 베스트 프랙티스 |

---

## 참고 문서

- **기획서**: `리웨어스_화면기획서_v1.2.md`
- **Figma**: Figma Talk to MCP 플러그인으로 연동

---

## 개발 시작 시 체크리스트

### Claude가 해야 할 일
1. [ ] CLAUDE.md "진행 상황" 섹션 확인
2. [ ] Figma MCP 채널 연결 (사용자에게 채널 ID 요청)
3. [ ] 다음 작업할 화면 확인
4. [ ] Figma에서 해당 화면 디자인 작업
5. [ ] 완료 후 "진행 상황" 섹션 업데이트

### 작업 완료 시
- [ ] CLAUDE.md "진행 상황" 업데이트
- [ ] 필요시 GitHub 커밋
