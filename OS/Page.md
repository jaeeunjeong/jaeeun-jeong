# Page Falut
Page Falut가 난 경우에도 cpu를 Page Falut가 발생한 것으로부터 뺏어서 (blocked 상태로 만듦)당장 cpu를 사용할수 있는 ready 상태 프로세스에 넘겨준다.
디스크에 요청한다. 디스크 컨트롤러에 요청한다. 새로운 거 쓰고 싶다고
그런 다음에 페이지 테이블 엔트리에다가 기록한다.  

# 메모리 
레퍼런스를 하려고보니까 invalid!  
-> trap이 걸림
-> cpu가 운영체제에 넘어감  
-> 운영체제는 Backing Store에 있는 곳에다가 올려놓음  
->해당하는 프레임 번호를 엔트리에다가 적고 valid로 변경  
-> cpu를 얻어서 주소 변환을 한다.
    
# 디스크에 접근하는 것은 시간이 많이 걸림.
-> 대부분은 페이지폴트가 안 나지만 엄청난 시간 소모
메모리 접근하는 시간 + 페이지 폴트 시간
OS로 cpu가 넘어와서 하드웨어 페이지 폴트를 처리하는 오버헤드 필요
빈  공간이 없으면 쫓아내고 디스크에서 읽어온 페이지 를 불러오는 작업
os가 vslid로 표시하고 cpu를 얻으면 restart하는 것 까지 매우 많음!!!
=> 메모리에서 이 작업을 해준다면??(잘 모르겠고) 알고리즘이 필요하다. 
