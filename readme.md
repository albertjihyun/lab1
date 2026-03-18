# 자재관리 CRUD 실습

---

## 0. 프로젝트 구조

```
content/
├── server.js
├── static/
│   ├── style.css
│   └── images/
│       └── tossbank-logo.png
└── templates/
    ├── material-list.html
    ├── material-write.html
    ├── material-detail.html
    ├── material-edit.html
    └── material-message.html
```
---

## 1. DB Table 구조

```
CREATE TABLE material (
    material_id INT PRIMARY KEY AUTO_INCREMENT,
    material_code VARCHAR(30) NOT NULL,
    material_name VARCHAR(150) NOT NULL,
    category VARCHAR(100) NOT NULL,
    specification VARCHAR(255) NOT NULL,
    unit VARCHAR(30) NOT NULL,
    unit_price INT NOT NULL,
    stock_qty INT NOT NULL,
    safety_stock INT NOT NULL,
    supplier_name VARCHAR(120) NOT NULL,
    warehouse_location VARCHAR(120) NOT NULL,
    inbound_date DATE NOT NULL,
    material_status VARCHAR(50) NOT NULL,
    manager_name VARCHAR(100) NOT NULL,
    manager_phone VARCHAR(30) NOT NULL,
    note TEXT NOT NULL,
    created_at DATETIME NOT NULL
);
```

---

## 1. 패키지 목록 업데이트

왜 필요하나?

* `apt install`은 패키지 저장소 정보를 기반으로 설치합니다.
* Colab VM은 새로 뜰 때마다 저장소 인덱스가 최신이 아닐 수 있어서 먼저 업데이트하는 게 안전합니다.
```
-- 1. 사용자 생성 (로컬 접속용)

CREATE USER 'newuser'@'localhost' IDENTIFIED BY '5678';

-- 2. testdb에 대한 모든 권한 부여
```
- 사용자 삭제 (DROP USER)

가장 간단한 방법으로, 계정 자체를 제거합니다.