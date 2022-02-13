# CRUD project #

### (1) Makefile을 만들어두어 더 효율적으로 컴파일 ###
  - Makefile 실행방법에는 총 3가지가 있습니다.
    
  1. 일반적인 출력은 make main 를 입력하여 파일들을 컴파일해줍니다. ./main 을 입력하여 실행해줍니다.
    
  2. 이때, debuging을 볼 수 있도록 실행할 수있는데 make main_debug 를 입력라고 똑같이 ./main을 입력하면 이번에는 전과 다르게 debugging 문구들까지 출력되는 것을 확인할 수 있습니다.
    
  3. make를 통해 만들어진 file들을 지우고 싶을 때에는 make clean 를 입력하여 remove해줍니다. 

<hr>

### (2) project 실행방법 ###  
  
  #### 1. 컴파일하고 실행하기 ####  
  - make를 통해 컴파일하고, ./main을 실행하였다면 "Menu : 1.Create 2.Read 3.Update 4.Delete 5.List 6.total_price 7.sort 8.import 9.Save 0.Quit > "이러한 메뉴판이 뜹니다. 원하는 기능에 해당하는 번호를 입력하시면 그 기능을 실행하게 됩니다.
    
  #### 2. 메뉴에 대한 설명 ####  
  - 1번은 record를 추가하는 기능을 가진 메뉴입니다.
    - 1번을 입력했을 경우,  저장가능한 record의 수는 maximum 100으로 잡아두었는데 record의 개수가 100개가 넘어서 저장공간이 없는 경우에 "There is no space!"를 출력합니다.
    - 저장 공간이 있다면 object(물건), price(가격), count(수량), name(주문자)를 입력하고
    - 만약 동일한 object를 주문한 name이 있다면 "Duplicated object&name!"를 출력하고
    - 모든 경우를 성공적으로 통과하여 record에 저장되었다면 "Complete!"를 출력합니다.
    
  - 2번은 특정한 이름을 입력받아 해당하는 name을 가지고 있는 모든 record를 출력해주는 기능을 가진 메뉴입니다.
    - 2번을 입력했을 경우, name을 입력하고 enter를 누르면 name을 가진 모든 record를 출력하는데, index도 같이 출력합니다.
      - 이때 index는 한 개의 name이 여러 object를 담을 수 있기 때문에 여러 object가 있을 때 몇 번째 정보인지 count된 수 입니다.
    - 만약 해당 이름이 없는 이름이라면 "No such name!"를 출력합니다.
    
  - 3번은 특정한 name과 object를 입력받아 해당 name과 object를 가지고 있는 record를 찾아 price와 count를 수정할 수 있는 기능을 가진 메뉴입니다.
    - 3번을 입력했을 경우, name과 object를 입력하면 해당 record의 price와 count를 수정할 수 있습니다. (name과 object는 수정X)
    - 성공적으로 입력되어 수정되었다면 "Complete!"를 출력하고
    - 일치하는 name은 있지만 해당 name을 가진 object가 없는 경우 & 일치하는 object는 있지만 해당 object를 가진 name이 없는 경우 & 두 개다 없는 경우에는 "No such object & name!"를 출력합니다.
    
  - 4번은 특정한 name과 object를 입력받아 해당 name과 object를 가지고 있는 record를 찾아 지우는 기능을 가진 메뉴입니다.
    - 4번을 입력했을 경우, name과 object를 입력하고
    - 만약 해당 name을 가지고 있으면서 동시에 해당 object를 가진 record가 있다면 지우고, "The record is deleted!"를 출력합니다.
    - 그러한 record가 없다면 "No such object & name!"를 출력합니다.
    
  - 5번은 모든 record들을 불러와 출력해주는 기능을 가진 메뉴입니다.
    - 5번을 입력했을 경우, 따로 입력받는 것없이 모든 record를 출력해줍니다.
    
  - 6번은 특정한 name의 total price를 계산해서 출력해주는 기능을 가진 메뉴입니다.
    - 6번을 입력했을 경우, name을 입력하고 그 name을 가진 record가 있다면 그 name을 가진 모든 record를 찾아 price를 다 더해서 total price를 구합니다.
    - 다 더해지면 "(name)'s total price >> (total price) 원"을 출력합니다.
    - 만약, 해당하는 name을 가진 record가 없다면 "No such name!"를 출력합니다.
    
  - 7번은 모든 record들을 오름차순으로 정렬해주는 기능을 가진 메뉴입니다.
    - 7번을 입력했을 경우, All data is sorted in ascending order of names. 1. Yes 0. No >  에서 번호를 입력받아서
    - 만약, 1을 입력했을 때에는 모든 record들을 오름차순으로 정렬하고 성공적으로 완료되었다면 "Complete!"를 출력합니다.
    - 만약, 0을 입력했을 때에는 메뉴판으로 돌아가고, 그외에 숫자를 입력했을 때에는 "Your answer is wrong!"를 출력하고 메뉴판으로 돌아갑니다.
    
  - 8번은 cart.txt파일에 저장된 모든 record들을 불러와서 현재 record에 하는 기능을 가진 메뉴입니다.
    - 8번을 입력했을 경우, All data will be deleted and new records will be reloaded. 1. Yes 0. No >  에서 번호를 입력받아
    - 만약, 1을 입력했을 때에는 현재 저장되어 있는 record를 모두 지우고 cart.txt에 있는 내용들로 바꿔주는데
      - 저장가능한 record의 수는 maximum 100까지로 그 이상의 record가 cart.txt에 있다면 "[Import] There is no space!"를 출력하고 100개까지만 저장됩니다.
    - 또 cart.txt안에 동일한 name과 object를 가진 record가 있다면 "[Import] Duplicated object(object) & name(name)!"을 출력하고 저장하지않고 건너뜁니다. 
    - 모든 경우를 성공적으로 통과하여 record에 저장되었다면 "(index) records are read from file!"를 출력합니다.
      - 이때 index는 성공적으로 저장된 record의 개수입니다.
    - 만약 0을 입력했을 때에는 메뉴판으로 돌아가고
    - 그외에 숫자를 입력했을 때에는 "Your answer is wrong!"를 출력하고 메뉴판으로 돌아갑니다.
    
  - 9번은 현재까지 저장된 record들을 가지고 ranking.txt과 cart.txt로 저장하는 기능을 가진 메뉴입니다.
    - 9번을 입력했을 경우, You choose one. 1. ranking top5(total price) 2. All records >  에서 번호를 입력받아
    - 만약, 1을 입력했을 때에는 현재까지 저장된 모든 records의 total price를 비교해서 가장 높은 price를 가진 name과 그 total price를 ranking.txt에 저장되는데 top 5까지만 저장되는 txt파일입니다.
      - 성공적으로 저장되었다면 "Complete!"를 출력합니다.
    - 만약 2를 입력했을 때에는 현재까지 저장된 모든 record들을 cart.txt에 저장합니다.
      - 성공적으로 저장되었다면 "(index) records are saved in file!"을 출력하는데 이때 index는 성공적으로 저장된 record의 개수입니다.
    - 그외에 숫자를 입력했을 때에는 "Your answer is wrong!"를 출력하고 메뉴판으로 돌아갑니다.
    
  - 0번은 말 그대로 실행한 main을 나가는 기능을 가진 메뉴입니다.
