![[Pasted image 20260710124723.png]]re.match() 


매칭 성공 케이스 (if result: )
Match 

.group() ,   .group(0)

.group()

if result:


1. 웹 크롤링이나 텍스트 데이터 수집할 때
웹 페이지를 긁어오거나 텍스트를 분석할 때, 앞뒤 쓸데없는 태그나 수식어는 버리고 진짜 정보만 쏙 빼올 때 사용합니다.

대상 문자열: "가격: 15,000원"

정규식 패턴: 가격:\s*(\d+,\d+)원

결과: group(0)은 "가격: 15,000원" 전체지만, group(1)을 쓰면 숫자와 쉼표로 된 알맹이인 "15,000"만 깔끔하게 주워 담을 수 있습니다.

2. 회원가입 및 이메일 검증할 때
사용자가 입력한 이메일이 올바른 형식인지 검사하면서, 동시에 아이디와 도메인을 분리해내고 싶을 때 씁니다.

대상 문자열: "sungjin-dev@gmail.com"

정규식 패턴: (\w+[-_.]?\w*)@(\w+\.\w+) (괄호를 두 개 사용)

결과: * group(1) ➡️ 이메일 ID인 "sungjin-dev"만 추출

group(2) ➡️ 도메인인 "gmail.com"만 추출

3. 로그 파일이나 파일 이름 파싱할 때
대량의 이미지 파일 이름에서 날짜나 순번만 추출해서 정리하고 싶을 때 사용합니다.

대상 문자열: "drone_photo_20260710.png"

정규식 패턴: drone_photo_(\d{8})\.png

결과: group(1)을 통해 "20260710"이라는 날짜 데이터만 쏙 뽑아내어 DB에 저장하거나 폴더별로 분류할 수 있습니다.

let inputField = document.getElementById('errorInput');
    
    // 2. 입력창 객체 안에서 사용자가 진짜로 타이핑한 '값(Value)'만 쏙 빼오기
    let targetData = inputField.value;

test() 메서드는 정규표현식의 결과를 아주 단순하게 "맞다/틀리다(True/False)"로만 딱 잘라 말해주는 녀석

test()는 파이썬이 아니라 자바스크립트(JavaScript)의 정규표현식 메서드
