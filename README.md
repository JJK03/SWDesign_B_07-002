# SWDesign_B_07-002

Maven 기반 Java 웹 애플리케이션 프로젝트입니다.

## Class Diagram

```mermaid
classDiagram
    class ReservationUI {
        +main(String[] args) void
    }

    class 예약정보 {
        -String 예약id
        -String id
        -String 객실id
        -int 숙박일자
        -int 숙박기간
        -double 총비용
        -고객정보 _user
        -객실정보 _room
        +예약정보()
        +예약(String id, String 객실id, int 숙박일자, int 숙박기간) double
    }

    class 고객정보 {
        +고객인증(String id) boolean
    }

    class 객실정보 {
        +객실조회(String 객실id) boolean
        +객실가격조회(String 객실id) double
    }

    ReservationUI ..> 예약정보 : creates / uses
    예약정보 *-- 고객정보 : _user
    예약정보 *-- 객실정보 : _room
```

## Project Structure

- `pom.xml`: Maven project configuration
- `src/main/webapp`: Web application resources
- `room`: Reservation domain classes

## Getting Started

```bash
mvn package
```

빌드 결과물은 `target/` 디렉터리에 생성됩니다.
