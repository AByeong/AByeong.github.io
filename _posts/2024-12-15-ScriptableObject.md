
---
title:  "ScriptableObject 강의 정리"
---

강의영상 링크: [강의영상](https://www.youtube.com/watch?v=UBt1Icebh1g)

**ScriptableObject**는 유니티 게임 개발에서 강력한 도구입니다. 단순한 데이터 컨테이너 이상의 역할을 수행하며, 효율적인 코드 관리와 협업을 위한 필수적인 요소입니다. 

# ScriptableObject

ScriptableObject(SO)는 MonoBehaviour(MB) 와 달리 GameObject나 Transform이 필요 없는 **단순한 데이터 컨테이너**입니다.  
**Asset**으로 존재하며, 런타임 중에 수정 가능한 데이터를 저장하고 공유하는 데 유용합니다. 

## ScriptableObject의 장점

* **메모리 절약:** 여러 GameObject가 같은 데이터를 참조할 때, 각각 데이터를 복제하는 대신 ScriptableObject를 참조하여 메모리를 효율적으로 사용합니다.
* **데이터와 로직 분리:** 데이터를 ScriptableObject에 저장하여 코드를 깔끔하게 유지하고, 데이터 변경이 코드에 미치는 영향을 최소화합니다. 
* **싱글톤 대체:** ScriptableObject는 싱글톤 패턴의 단점을 해결하고, 전역적인 데이터 접근을 효율적으로 관리합니다.
* **플레이 모드와 에디터 모드 간 데이터 유지:** ScriptableObject는 플레이 모드와 에디터 모드를 전환해도 데이터가 초기화되지 않습니다.
* **직렬화:** Inspector 창에서 데이터를 직접 수정하고 저장할 수 있어 편리합니다.
* **협업:** 여러 개발자가 ScriptableObject를 공유하여 효율적인 협업 환경을 구축할 수 있습니다.

## ScriptableObject 활용법 

ScriptableObject는 디자인 패턴에 활용될 수 있습니다.  

### 1. Extendable Enums:

기존 enum의 한계를 극복하고, **확장 가능한 enum을 구현**할 수 있습니다. 예를 들어, 가위, 바위, 보 게임에서 각 속성을 ScriptableObject로 정의하고, 추가적인 속성을 쉽게 추가할 수 있습니다. 

### 2. Delegate Objects (전략 패턴): 

ScriptableObject에 메서드를 정의하여 **Delegate처럼 활용**할 수 있습니다. 상태를 ScriptableObject로 저장하고, 필요에 따라 다른 ScriptableObject로 교체하여 객체의 동작을 변경할 수 있습니다. 

### 3. Singleton: 

ScriptableObject를 사용하여 **싱글톤 패턴을 대체**하고, 전역적인 데이터 접근을 효율적으로 관리할 수 있습니다. 

### 4. Observer: 

**ScriptableObject를 Event Channel**로 활용하여 Observer 패턴을 구현할 수 있습니다. Publisher는 ScriptableObject에 이벤트를 발행하고, Observer들은 이를 구독하여 이벤트 발생 시 특정 동작을 수행합니다. 

### 5. Command: 

ScriptableObject를 Command 객체로 사용하여 **명령을 캡슐화**하고 재사용할 수 있습니다. 

### 6. Runtime Sets: 

게임 내 여러 목록을 ScriptableObject로 관리하여 **싱글톤 없이 효율적으로 데이터를 관리**할 수 있습니다. 

## 게임 데이터 관리 

ScriptableObject는 **게임 데이터를 관리**하는 데 매우 유용합니다. 예를 들어, 아이템, 캐릭터, 레벨 정보 등을 ScriptableObject로 저장하고, Inspector 창에서 편리하게 수정할 수 있습니다. 

## 협업 및 데이터 관리 

ScriptableObject는 JSON, XML과 같은 **외부 데이터 형식과 연동**하여 사용할 수도 있습니다. 외부 툴에서 데이터를 편집하고 ScriptableObject로 변환하여 유니티 프로젝트에 적용하면 협업 효율을 높일 수 있습니다. 
XML, JSON파일은 외부툴로 편집이 가능하고, Scriptableobject는 Unity Editor에 특화된 것이기에 변환 과정이 필요하다.
