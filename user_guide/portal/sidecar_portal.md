### [Index](https://github.com/K-PaaS/Guide/blob/master/README.md) > [Sidecar User Guide](../README.md) > 포탈 사용 가이드

## Table of Contents

1. [문서 개요](#1)
   * [1.1. 목적](#1-1)
   * [1.2. 범위](#1-2)
2. [Sidecar 플랫폼 포털 접속](#3)
   * [2.1. 컨테이너 플랫폼 포털 관리자 계정 로그인](#2-1)
   * [2.2. Sidecar 플랫폼 포털 계정 로그인](#2-2)
3. [Sidecar 플랫폼 포털 구성](#3)
   * [3.1. Sidecar 플랫폼 포털 사용자 권한 유형](#3-1)
   * [3.2. Sidecar 플랫폼 포털 메뉴 구성](#3-2)
4. [Sidecar 플랫폼 포털 메뉴 설명](#4)
   * [4.1. Sidecar 메뉴](#4-1)
   * [4.1.1. Overview](#4-1-1)
   * [4.2. Workloads 메뉴](#4-2)
   * [4.2.1. Apps](#4-2-1)
   * [4.3. Resources 메뉴](#4-3)
   * [4.3.1. Domains](#4-3-1)
   * [4.3.2. Routes](#4-3-2)
   * [4.3.3. Services](#4-3-3)
   * [4.4. Managementes 메뉴](#4-4)
   * [4.4.1. Sidecar Users](#4-4-1)
   * [4.4.2. Organizations](#4-4-2)
   * [4.5. Info 메뉴](#4-5)
   * [4.5.1. Access](#4-5-1)






<br>


# <div id='1'/> 1. 문서 개요

## <div id='1-1'/> 1.1. 목적
본 문서는 Sidecar 플랫폼 포털 사용 방법에 대해 기술하였다.

<br>

## <div id='1-2'/> 1.2. 범위
본 문서는 Windows 환경을 기준으로 Sidecar 플랫폼 포털의 사용 방법에 대해 기술하였다.

<br>

# <div id='2'>2. Sidecar 플랫폼 포털 접속
Sidecar 플랫폼 포털에 접속한다.<br><br>
**Sidecar 플랫폼 포털 URL** : `http://sidecar-portal-ui.apps.${SYSTEM_DOMAIN}`
+ [[2.4. variable 설정]](../../install/sidecar.md#2.4) 에서 정의한 `system_domain` 값 입력

<br>

## <div id='2-1'/>2.1. 컨테이너 플랫폼 포털 관리자 계정 로그인
Sidecar 플랫폼의 포털은 컨테이너 관리자 계정과 동일하다.  
컨테이너 관리자 계정은 Sidecar의 리소스를 확인할 수 있으며, 생성한 계정의 접근권한에 대한 설정이 가능하다.  
컨테이너 관리자 계정은 패스워드 초기화 설정이 필요하므로 다음 링크 내용을 참조하여 선처리한다.  

[컨테이너 플랫폼 포털 관리자 계정 패스워드 설정](https://github.com/K-PaaS/container-platform/blob/master/use-guide/portal/container-platform-portal-guide.md#-key-%EC%BB%A8%ED%85%8C%EC%9D%B4%EB%84%88-%ED%94%8C%EB%9E%AB%ED%8F%BC-%ED%8F%AC%ED%84%B8-%EA%B4%80%EB%A6%AC%EC%9E%90-%EA%B3%84%EC%A0%95-%ED%8C%A8%EC%8A%A4%EC%9B%8C%EB%93%9C-%EC%84%A4%EC%A0%95-)

- 관리자 계정으로 컨테이너 플랫폼 포털에 로그인한다.
   + **Username** : `admin`
   + **Password** : `초기화한 패스워드 값`

![image 002]

<br>

## <div id='2-2'/>2.2. Sidecar 플랫폼 포털 계정 로그인
### 사용자 회원가입
- 하단의 'Register' 버튼을 클릭한다.

![image 003]

- 등록할 사용자 계정정보를 입력 후 'Register' 버튼을 클릭하여 Sidecar 플랫폼 포털에 회원가입한다.

![image 004]

- 회원가입 후 바로 포털 접속이 불가하며 관리자로부터 해당 사용자가 이용할 Sidecar Role을 할당 받은 후 포털 이용이 가능하다.  
  사용자에게 Sidecar Role 할당 및 Org & Space 할당은 [[4.4. Managementes 메뉴]](#4-4) 를 참고한다.

![image 005]

### 사용자 로그인
- 회원가입을 통해 등록된 계정으로 Sidecar 플랫폼 포털에 로그인한다.

![image 006]

<br>    

# <div id='3'/> 3. Sidecar 플랫폼 포털 구성
## <div id='3-1'/> 3.1. Sidecar 플랫폼 포털 사용자 권한 유형
| <center>사용자 유형</center> | <center>기능</center> |
| :--- | :--- |
| Super Admin (전체 관리자) | Sidecar 플랫폼 사용자 관리 권한  |
| Sidecar Admin (Sidecar 관리자) | Sidecar 플랫폼 리소스 관리 권한  |
| User (일반 사용자) | 할당된 클러스터 내 동작 권한|

<br>

## <div id='3-2'/> 3.2. Sidecar 플랫폼 포털 메뉴 구성
<table style="table-layout: fixed; width: 816px;">
<colgroup>
<col style="width: 126px">
<col style="width: 174px">
<col style="width: 307px">
<col style="width: 209px">
</colgroup>
<thead>
  <tr>
    <th>메뉴</th>
    <th>분류</th>
    <th>설명</th>
    <th>접근 권한</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>Sidecar</td>
    <td>Overview</td>
    <td>Sidecar 플랫폼 Space 내 리소스 대시보드</td>
    <td>All</td>
  </tr>
  <tr>
    <td>Workloads</td>
    <td>Apps</td>
    <td>Apps 정보 관리</td>
    <td>All</td>
  </tr>
  <tr>
    <td rowspan="3">Services</td>
    <td>Domains</td>
    <td>Domains 정보 관리</td>
    <td rowspan="3">All</td>
  </tr>
  <tr>
    <td>Routes</td>
    <td>Routes 정보 관리</td>
  </tr>
  <tr>
    <td>Routes</td>
    <td>Routes 정보 관리</td>
  </tr>
  <tr>
    <td rowspan="2">Managementes 메뉴</td>
    <td>Sidecar Users</td>
    <td>Sidecar Users 정보 관리</td>
    <td>Super Admin</td>
  </tr>
  <tr>
    <td>Organizations</td>
    <td>Organizations, Space 정보 관리</td>
    <td>Super Admin, Sidecar Admin, User(Role 별 상이)</td>
  </tr> 
  <tr>
    <td>Info</td>
    <td>Access</td>
    <td>CLI 사용을 위한 환경 설정 정보 관리</td>
    <td>All</td>
  </tr>
</tbody>
</table>

<br>

# <div id='4'/> 4. Sidecar 플랫폼 포털 메뉴 설명
본 장에서는 Sidecar 플랫폼 포털의 메뉴에 대한 설명을 기술하였다.

<br>

## <div id='4-1'/> 4.1. Sidecar 메뉴
### <div id='4-1-1'/> 4.1.1. Overview
#### <div id='4-1-1-1'/> 4.1.1.1. Overview 정보 조회
- App, Pod의 개수와 차트를 조회한다.  

![4-1-1-1]


<br>

## <div id='4-2'/> 4.2. Workloads 메뉴
### <div id='4-2-1'/> 4.2.1. Apps
#### <div id='4-2-1-1'/> 4.2.1.1. App 목록
- Workloads의 Apps를 클릭하여 App 목록 페이지로 이동한다.

![4-2-1-1]

<br>

#### <div id='4-2-1-2'/> 4.2.1.2. App 추가(배포)
- App 목록에서 추가 버튼을 클릭할 시 App 추가 팝업창이 뜬다.
- App 추가 팝업창에서 이름, Route, Memory, Disk, File을 지정할 수 있다.

![4-2-1-2]

<br>

#### <div id='4-2-1-3'/> 4.2.1.3. App 상세
- App 목록에서 App명을 클릭하여 App 상세 페이지로 이동한다.  
- App 상세 페이지는 App 정보, App Instances, App Service, App Environment, App Route, App Log 확인이 가능하다.  

![4-2-1-3]
<br>

##### <div id='4-2-1-3-1'/> 4.2.1.3.1. App 정보
- App의 기본 정보 확인이 가능하다.
<br>

###### <div id='4-2-1-3-1-1'/> 4.2.1.3.1.1. App 이름 변경
- Name항목을 수정하여 저장 버튼을 클릭 할 시 App 이름 변경이 가능하다.
<br>

 ###### <div id='4-2-1-3-1-2'/> 4.2.1.3.1.2. App Instances 변경
- Instance항목을 수정하여 저장 버튼을 클릭 할 시 App Instances 변경이 가능하다.
<br>

###### <div id='4-2-1-3-1-4'/> 4.2.1.3.1.4. App Memory 변경
- Memory항목을 수정하여 저장 버튼을 클릭 할 시 App Memory 변경이 가능하다.
<br>

###### <div id='4-2-1-3-1-5'/> 4.2.1.3.1.5. App Disk 변경
- Disk항목을 수정하여 저장 버튼을 클릭 할 시 App Disk 변경이 가능하다.
<br>

###### <div id='4-2-1-3-1-6'/> 4.2.1.3.1.6. App 시작/중지
- State항목의 버튼을 클릭 할 시 App 시작/중지가 가능하다.
<br>

##### <div id='4-2-1-3-2'/> 4.2.1.3.2. App Instances
- App의 Instance 별 리소스 사용량과 상태 확인이 가능하다.
<br>

##### <div id='4-2-1-3-3'/> 4.2.1.3.3. App Services
- Service App Bind 목록 확인이 가능하다.

![4-2-1-3-3]
<br>

###### <div id='4-2-1-3-3-1'/> 4.2.1.2.3.1. App-Service 연결
- Service App Bind 목록에서 연결 버튼을 클릭할 시 Service 연결 팝업창이 뜬다.  

![4-2-1-3-3-1]  
<br>

###### <div id='4-2-1-3-3-2'/> 4.2.1.3.3.2. Service Credentials 조회
- Service App Bind 목록에서 Credentials 버튼을 클릭할 시 Service Credentials 조회 팝업창이 뜬다.  

![4-2-1-3-3-2]
<br>

###### <div id='4-2-1-3-3-3'/> 4.2.1.3.3.3. App-Service 연결 해제
- Service App Bind 목록에서 Disconnect 버튼을 클릭할 시 App과 Service 연결이 해제된다.  

![4-2-1-3-3-3]
<br>

##### <div id='4-2-1-3-4'/> 4.2.1.3.4. App Environment
- App의 Environment Variable와 System Environment 조회가 가능하다.

![4-2-1-3-4]
<br>

###### <div id='4-2-1-3-4-1'/> 4.2.1.3.4.1. App Environment 추가
- App의 Environment Variable 목록에서 추가 버튼을 클릭할 시 환경변수 추가 팝업창이 뜬다.  
- App의 Environment Variable 추가 팝업창에서 Key, Value을 지정할 수 있다.

![4-2-1-3-4-1]

<br>

###### <div id='4-2-1-3-4-2'/> 4.2.1.3.4.2. App Environment 수정
- Value칸을 수정하여 저장 버튼을 클릭 할 시 App Environment 수정이 가능하다. 

![4-2-1-3-4-2]

<br>

###### <div id='4-2-1-3-4-3'/> 4.2.1.3.4.3. App Environment 삭제
- App의 Environment Variable 목록에서 삭제 버튼을 클릭할 시 환경변수 삭제가 가능하다.  

![4-2-1-3-4-3]

<br>

##### <div id='4-2-1-3-5'/> 4.2.1.3.5. App Routes
- Route App Bind 목록 확인이 가능하다.

![4-2-1-3-5]
<br>

###### <div id='4-2-1-3-5-1'/> 4.2.1.3.5.1. App-Routes 연결
- Route App Bind 목록에서 연결 버튼을 클릭할 시 Route 연결 팝업창이 뜬다.  

![4-2-1-3-5-1]

<br>

###### <div id='4-2-1-3-5-2'/> 4.2.1.3.5.2. App-Routes 연결 해제
- Route App Bind 목록에서 Disconnect 버튼을 클릭할 시 App과 Route 연결이 해제된다.  

![4-2-1-3-5-2]

<br>

##### <div id='4-2-1-3-6'/> 4.2.1.3.6. App Log 조회
- App의 Log 확인이 가능하다.  

![4-2-1-3-6]

<br>

##### <div id='4-2-1-3-7'/> 4.2.1.3.7. App 삭제
- 우측 하단의 삭제 버튼을 클릭할 시 App 삭제가 가능하다.

![4-2-1-3-7]

<br>

## <div id='4-3'/> 4.3. Resources 메뉴
### <div id='4-3-1'/> 4.3.1. Domains
#### <div id='4-3-1-1'/> 4.3.1.1. Domain 목록
- Resources의 Domains를 클릭하여 Domain 목록 페이지로 이동한다.  

![4-3-1-1]

<br>

#### <div id='4-3-1-2'/> 4.3.1.2. Domain 추가
- Domain 목록에서 추가 버튼을 클릭할 시 Domain 추가 팝업창이 뜬다.  

![4-3-1-2]

<br>

#### <div id='4-3-1-3'/> 4.3.1.3. Domain 삭제
- Domain 목록에서 삭제 버튼을 클릭할 시 Domain이 삭제된다.  

![4-3-1-3]

<br>

### <div id='4-3-2'/> 4.3.2. Routes
#### <div id='4-3-2-1'/> 4.3.2.1. Route 목록
- Resources의 Routes를 클릭하여 Route 목록 페이지로 이동한다.  

![4-3-2-1]

<br>

#### <div id='4-3-2-2'/> 4.3.2.2. Route 추가
- Route 목록에서 추가 버튼을 클릭할 시 Route 추가 팝업창이 뜬다.  
- Route 추가 팝업창에서 Host, Domain, Path(선택)를 지정할 수 있다.

![4-3-2-2]

<br>

#### <div id='4-3-2-3'/> 4.3.2.3. Route 삭제
- Route 목록에서 삭제 버튼을 클릭할 시 Route가 삭제된다.  

![4-3-2-3]

<br>

#### <div id='4-3-2-4'/> 4.3.2.4. Route 상세
- Route 목록에서 Route명을 클릭하여 Route 상세 페이지로 이동한다.  
- Route 상세 페이지는 Route 정보, Route App Bind 목록 확인이 가능하다.

![4-3-2-4]

<br>

##### <div id='4-3-2-4-1'/> 4.3.2.4.1. App-Route 연결 해제
- Route App Bind 목록에서 삭제 버튼을 클릭할 시 App과 Route의 연결이 해제 된다.  

<br>

##### <div id='4-3-2-4-2'/> 4.3.2.4.2. Route 삭제
- Route 상세에서 삭제 버튼을 클릭할 시 Route가 삭제된다.  

<br>

### <div id='4-3-3'/> 4.3.3. Services
#### <div id='4-3-3-1'/> 4.3.3.1. Service 목록
- Resources의 Services를 클릭하여 Service 목록 페이지로 이동한다.  

![4-3-3-1]

<br>

#### <div id='4-3-3-2'/> 4.3.3.2. Service 추가
- Service 목록에서 추가 버튼을 클릭할 시 Service 추가 팝업창이 뜬다.  
- Service 추가 팝업창에서 이름, Credentials(JSON)를 지정할 수 있다.

![4-3-3-2]

<br>

#### <div id='4-3-3-3'/> 4.3.3.3. Service 삭제
- Service 목록에서 삭제 버튼을 클릭할 시 Service가 삭제된다.  

![4-3-3-3]

<br>

#### <div id='4-3-3-4'/> 4.3.3.4. Service 상세
- Service 목록에서 Service명을 클릭하여 Service 상세 페이지로 이동한다.  
- Service 상세 페이지는 Service 정보, Service App Bind 목록 확인이 가능하다.

![4-3-3-4]

<br>

##### <div id='4-3-3-2-1'/> 4.3.1.1.1. Service Credential 수정
- Service 상세에서 Credential의 Edit를 클릭하여 Credential 수정이 가능하다.  

<br>

##### <div id='4-3-3-2-2'/> 4.3.1.1.2. App-Service 연결 해제
- Service App Bind 목록에서 삭제 버튼을 클릭할 시 App과 Service의 연결이 해제 된다.  

<br>

##### <div id='4-3-3-2-3'/> 4.3.3.2.3. Service 삭제
- Service 상세에서 삭제 버튼을 클릭할 시 Service가 삭제된다.  

<br>

## <div id='4-4'/> 4.4. Managements 메뉴
### <div id='4-4-1'/> 4.4.1. Sidecar Users
#### <div id='4-4-1-1'/> 4.4.1.1. 클러스터 관리자 목록
- Managements 메뉴의 Users를 선택하고 Administrator탭을 클릭하여 클러스터 관리자를 조회한다.  

![4-4-1-1]

<br>

#### <div id='4-4-1-2'/> 4.4.1.2. 클러스터 관리자 상세
- 클러스터 관리자 User ID를 클릭하여 클러스터 관리자 상세 조회 페이지로 이동한다.  

![4-4-1-2]

<br>

##### <div id='4-4-1-2-1'/> 4.4.1.2.1. Sidecar Role 수정
- User 상세에서 수정 버튼을 클릭하여 User 수정 페이지로 이동한다.  
- User 수정 페이지에서 해당 사용자에게 Sidecar 관리자(Sidecar Admin) 또는 Sidecar 사용자(Sidecar User) 권한 할당이 가능하다.  

![4-4-1-2-1]

<br>

#### <div id='4-4-1-3'/> 4.4.1.3. Sidecar 일반 사용자 목록
- Managements 메뉴의 Users를 선택하고 User탭을 클릭하여 사용자 목록을 조회한다.  
  - 활성(Active) 탭 : Sidecar 내 사용 권한이 활성화된 사용자 목록  
  ![4-4-1-3_1]
  - 비활성(Inactive) 탭 : Sidecar 내 사용 권한이 비활성화된 사용자 목록  
  ![4-4-1-3_2]

<br>

#### <div id='4-4-1-4'/> 4.4.1.4. Sidecar 일반 사용자 상세
- User ID를 클릭하여 일반 사용자 상세 조회 페이지로 이동한다.  

![4-4-1-4]

<br>

##### <div id='4-4-1-4-1'/> 4.4.1.4.1. Sidecar Role 수정
- User 상세에서 수정 버튼을 클릭하여 User 수정 페이지로 이동한다.  
- User 수정 페이지에서 해당 사용자에게 Sidecar 관리자(Sidecar Admin) 또는 Sidecar 사용자(Sidecar User) 권한 할당이 가능하다.  

![4-4-1-4-1]

<br>

### <div id='4-4-2'/> 4.4.2. Organizations
#### <div id='4-4-2-1'/> 4.4.2.1. Organization 목록
- Managements의 Organizations을 클릭하여 Organization 목록 페이지로 이동한다.  

![4-4-2-1]

<br>

#### <div id='4-4-2-2'/> 4.4.2.2. Organization 추가
- Organization 목록에서 추가 버튼을 클릭할 시 Organization 추가 팝업창이 뜬다.  

![4-4-2-2]

<br>

#### <div id='4-4-2-3'/> 4.4.2.3. Organization 상세
- Organization 목록에서 Organization명을 클릭하여 Organization 상세 페이지로 이동한다.  
- Organization 상세 페이지는 Org 정보, Organization User 목록, Space 목록 확인이 가능하다.

![4-4-2-3]

<br>

##### <div id='4-4-2-3-1'/> 4.4.2.3.1. Organization User 추가
- Organization User 목록에서 추가 버튼을 클릭할 시 Organization User 추가 팝업창이 뜬다.
- Organization User는 Organization User와 Organization Manager 선택이 가능하다.

![4-4-2-3-1]

<br>

##### <div id='4-4-2-3-2'/> 4.4.2.3.2. Organization User 권한 설정
- Organization User 목록에서 Org Role을 클릭하여 Organization User 권한 설정이 가능하다.  

![4-4-2-3-2]

<br>

##### <div id='4-4-2-3-3'/> 4.4.2.3.3. Space 추가
- Space 목록에서 추가 버튼을 클릭할 시 Space 추가 팝업창이 뜬다.

![4-4-2-3-3]

<br>

##### <div id='4-4-2-3-4'/> 4.4.2.3.4. Space 상세
- Space 목록에서 Space명을 클릭하여 Space 상세 페이지로 이동한다.  

![4-4-2-3-4]

<br>

###### <div id='4-4-2-3-4-1'/> 4.4.2.3.4.1. Space User 추가
- Space User 목록에서 추가 버튼을 클릭할 시 Space User 추가 팝업창이 뜬다.
- Organization에 소속된 User만 Space User로 초대가 가능하다
- Space User는 Space Developer와 Space Manager 선택이 가능하다.

![4-4-2-3-4-1]

<br>


###### <div id='4-4-2-3-4-2'/> 4.4.2.3.4.2. Space User 권한 설정
- Space User 목록에서 Space Role을 클릭하여 Space User 권한 설정이 가능하다.

![4-4-2-3-4-2]

<br>


## <div id='4-5'/> 4.5. Info 메뉴
### <div id='4-5-1'/> 4.5.1. Access
#### <div id='4-5-1-1'/> 4.5.1.1. Access 상세
- User Info 정보를 조회한다.  
- Sidecar 플랫폼의 CLI 사용을 위한 환경 및 사용 설정 정보를 조회한다.  

![4-5-1-1]



----
[image 002]:../images/portal/cp-002.png
[image 003]:../images/portal/cp-003.png
[image 004]:../images/portal/cp-004.png
[image 005]:../images/portal/cp-005.png
[image 006]:../images/portal/cp-006.png
[4-1-1-1]:../images/portal/4-1-1-1.jpeg
[4-2-1-1]:../images/portal/4-2-1-1.jpeg
[4-2-1-2]:../images/portal/4-2-1-2.jpeg
[4-2-1-3]:../images/portal/4-2-1-3.jpeg
[4-2-1-3-3]:../images/portal/4-2-1-3-3.jpeg
[4-2-1-4-1]:../images/portal/4-2-1-4-1.jpeg
[4-2-1-4-2]:../images/portal/4-2-1-4-2.jpeg
[4-2-1-5-1]:../images/portal/4-2-1-5-1.jpeg
[4-2-1-5]:../images/portal/4-2-1-5.jpeg
[4-2-1-6-1]:../images/portal/4-2-1-6-1.jpeg
[4-2-1-6]:../images/portal/4-2-1-6.jpeg
[4-2-1-7]:../images/portal/4-2-1-7.jpeg
[4-2-1-8]:../images/portal/4-2-1-8.jpeg
[4-2-1-3-3-1]:../images/portal/4-2-1-3-3-1.jpeg
[4-2-1-3-3-2]:../images/portal/4-2-1-3-3-2.jpeg
[4-2-1-3-3-3]:../images/portal/4-2-1-3-3-3.jpeg
[4-2-1-3-4]:../images/portal/4-2-1-3-4.jpeg
[4-2-1-3-4-1]:../images/portal/4-2-1-3-4-1.jpeg
[4-2-1-3-4-2]:../images/portal/4-2-1-3-4-2.jpeg
[4-2-1-3-4-3]:../images/portal/4-2-1-3-4-3.jpeg
[4-2-1-3-5]:../images/portal/4-2-1-3-5.jpeg
[4-2-1-3-5-1]:../images/portal/4-2-1-3-5-1.jpeg
[4-2-1-3-5-2]:../images/portal/4-2-1-3-5-2.jpeg
[4-2-1-3-6]:../images/portal/4-2-1-3-6.jpeg
[4-2-1-3-7]:../images/portal/4-2-1-3-7.jpeg
[4-3-1-1-1]:../images/portal/4-3-1-1-1.jpeg
[4-3-1-1]:../images/portal/4-3-1-1.jpeg
[4-3-1-2]:../images/portal/4-3-1-2.jpeg
[4-3-1-3]:../images/portal/4-3-1-3.jpeg
[4-3-2-1-1]:../images/portal/4-3-2-1-1.jpeg
[4-3-2-1]:../images/portal/4-3-2-1.jpeg
[4-3-2-2]:../images/portal/4-3-2-2.jpeg
[4-3-2-3]:../images/portal/4-3-2-3.jpeg
[4-3-2-4]:../images/portal/4-3-2-4.jpeg
[4-3-3-1-1]:../images/portal/4-3-3-1-1.jpeg
[4-3-3-1]:../images/portal/4-3-3-1.jpeg
[4-3-3-2]:../images/portal/4-3-3-2.jpeg
[4-3-3-3]:../images/portal/4-3-3-3.jpeg
[4-3-3-4]:../images/portal/4-3-3-4.jpeg
[4-4-1-1]:../images/portal/4-4-1-1.jpeg
[4-4-1-2-1]:../images/portal/4-4-1-2-1.jpeg
[4-4-1-2]:../images/portal/4-4-1-2.jpeg
[4-4-1-3_1]:../images/portal/4-4-1-3_1.jpeg
[4-4-1-3_2]:../images/portal/4-4-1-3_2.jpeg
[4-4-1-3_1]:../images/portal/4-4-1-3_1.jpeg
[4-4-1-4-1]:../images/portal/4-4-1-4-1.jpeg
[4-4-1-4]:../images/portal/4-4-1-4.jpeg
[4-4-2-1]:../images/portal/4-4-2-1.jpeg
[4-4-2-2-1]:../images/portal/4-4-2-2-1.jpeg
[4-4-2-2-3]:../images/portal/4-4-2-2-3.jpeg
[4-4-2-2-4-1]:../images/portal/4-4-2-2-4-1.jpeg
[4-4-2-2-4]:../images/portal/4-4-2-2-4.jpeg
[4-4-2-2]:../images/portal/4-4-2-2.jpeg
[4-4-2-3]:../images/portal/4-4-2-3.jpeg
[4-4-2-3-1]:../images/portal/4-4-2-3-1.jpeg
[4-4-2-3-2]:../images/portal/4-4-2-3-2.jpeg
[4-4-2-3-3]:../images/portal/4-4-2-3-3.jpeg
[4-4-2-3-4]:../images/portal/4-4-2-3-4.jpeg
[4-4-2-3-4-1]:../images/portal/4-4-2-3-4-1.jpeg
[4-4-2-3-4-2]:../images/portal/4-4-2-3-4-2.jpeg
[4-5-1-1]:../images/portal/4-5-1-1.jpeg

### [Index](https://github.com/K-PaaS/Guide/blob/master/README.md) > [Sidecar User Guide](../README.md) > 포탈 사용 가이드
