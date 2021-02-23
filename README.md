# vue

## 업무일지

### 02/17
셀트리온 Remsimate App.의 다국적 contents 관련 수정 사항 
 
- 오타 수정
      Main 화면 내 Resmima 오타입니다. Remsima 로 수정 부탁 드립니다. 
                     <image001.png>
 
- 동영상 링크 적용
                     <image003.jpg> 
 1번 아이콘 (Pre-filled pen video)
 https://youtu.be/q0PvjlJDc2c
 2번 아이콘 (Pre-filled syringe video)
 https://youtu.be/0tZTqbZLHHM
  (완료)

Education, EducationPdf, EducationPdf3 
this.geoLocation = "AU";
ES,  IE , GB
변경 후 커밋,푸시하고 모바일앱으로 확인 후 
각 나라 별 스크린샷 
호주, 스페인, 아일랜드 ,영국
(완료) 


### 02/18 

지출결의서 작성하면서 아래 빈칸에 
내용을 작성하고 결재를 누르면 맨 윗줄이 날라가는 
증상이 종종 발생 (매번 그러는 것도 아님)
저만 그런 줄 알고 그냥 썼었는데 보니까 다른 분들도
동일한 오류가 발생

오류 수정 요청 들어옴 

### 02/19

테스트 아이디 
KSUPERMIN / 1234
2099001N /1234

	
o 특정 알림에 체크해도 알림이 표시되지 않음
결재알림, 게시판 알림은 전혀 오지 않으나 업무지원요청 관련 알림은 옵니다.

마이페이지 알림설정 오류 파악중

### 02/22
<<에디터 내용입력 오류사항(**완료**)>>by Judy 
지출결의서 관련 기안의 경우
docText를 html로 변환하는데
1. 에디터에서 첫번째 문장을 <>태그로 감싸지않고 그냥 text 처리되었을경우
html 변환처리가 안되고 전체 text 처리되어 넘어감 - 첫줄 잘림 현상 X
2. 모든 문장이 <>로 감싸지는경우 docText를 html로 변환하고 각 object마다 outerHTML을 text에  append하는데 반복문 초기값을 1로 설정하여 첫번째 줄이 날아가는 현상

전체검색으로 'jQuery(' 검색해서
text를 html로 변환하며 하단에 반복문을 통해 content에 변환한 text를 append 하는 경우만 수정함

for(let i = 1;
=> for(let i = 0;

ApprViewProcess.js - 134
ApprView.vue - 435
ApprViewMode.vue - 307
Draft.vue - 989


미팅
결정된 사항
- 3월 중순까지 셀트리온 관리자 등 완료
- 2월 말까지 그룹웨어 모든 오류 사항 수정 완료
- 현재까지 온 오류, 확인 사항 엑셀 정리 후 써스(대표님)께 제출(완료)


### 02/23(화)

<오늘의 에러>
▶ [ERROR] 2021-02-23 13:17:43.911 [http-nio-9090-exec-5] com.kaonsoft.groupware.common.utility.LogUtility[error:130] - [com.kaonsoft.groupware.mainframe.controller.project.WorkSupportRequestManageController.getExcelList] org.mybatis.spring.MyBatisSystemException: nested exception is org.apache.ibatis.binding.BindingException: Parameter 'writeDateFrom' not found. Available parameters are [arg0, param1, status, param2]


해결 방법 -> 
	1. T_BZ_WORKSUPP_REQ_Mapper.xml 에 
	<select id="getExcelListForHq" parameterType="BzWorkSupportSearchRequestVO" resultType="BzWorkSuppRequestMngDTO"> 가 있는데
	parameterType이 BzWorkSupportSearchRequestVO" 인데 
	IBzWorkSupportReqMapper.java 안에 
	List<BzWorkSuppRequestMngDTO> getExcelListForHq(final BzWorkSupportSearchRequestVO vo); 부분에 
	List<BzWorkSuppRequestMngDTO> getExcelListForHq(final BzWorkSupportSearchRequestVO vo, String status); 로 해놓음;;
	parameterType이 두개일 순 없다.. 
	
	
	2.
	 <if test="checked != null and checked != ''">
                AND REQ.STATUS IN
                <foreach collection="checked" open="(" close=")" item="checked" separator=",">
                    #{checked}
                </foreach>
            </if>
		   <!-- <choose>
	           <when test = "checked != null and checked != ''">
	            AND   REQ.STATUS = #{checked}
	           </when>
	           <otherwise>
				AND   REQ.STATUS = '0004'
			   </otherwise>
		   </choose>  -->
		
	vo에서 checked는 String[] checked; 여서 foreach 문으로 돌려줘야한다. 
	밑에 <choose> 주석이 전 버전 


 **엑셀 다운로드 오류** : 
o 업무지원요청관리 엑셀 출력시, 다른 조건을 입력하더라도 동일한 값 출력됨
업무지원요청관리에서 검색 시, 일자구분(작성일자,수행일자,요청일자)를 선택하여 값을 출력할 수 있는데 어느 일자를 선택하더라도 동일한 값이 출력됩니다. 구분에 알맞는 값이 출력되었으면 합니다.  (**완료**)
TechHQ.vue
BzWorkSupportReqMngServiceImpl.java
T_BZ_WORKSUPP_REQ_Mapper.xml
IBzWorkSupportReqMapper.java
WorkSupportRequestManageController.java



 **activeMQ** 

실행하는법 : 최신 버전 다운로드 후 (http://activemq.apache.org/) 
	     압축 풀고 cmd 로 /bin 까지가서 activemq start 입력
	     그럼 실행된다.
activeMQ 실행 상황 보는 사이트(http://localhost:8161/admin) 
id : admin / pw: admin


### 02/24(수)

알림 
