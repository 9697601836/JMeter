# JMeter

HW_1

Сделать сценарий с перечисленными эндпоинтами

Дать нагрузку на 50, 250, 500 потоков.
Настройки Jmeter - файл .jmx выгружаем на гит.

http://162.55.220.72:5005

1) http://162.55.220.72:5005/get_method
req.
GET
name: str
age: int


2) http://162.55.220.72:5005/user_info_2
req.
POST
name: str
age: int
salary: int


3) http://162.55.220.72:5005/user_info_3
req.
POST
name: str
age: int
salary: int

4) http://162.55.220.72:5005/object_info_1
req.
GET
name: str
age: int
weight: int

5) http://162.55.220.72:5005/object_info_2
req.
GET
name: str
age: int
salary: int

6) http://162.55.220.72:5005/object_info_3
req.
GET
name: str
age: int
salary: int

7) http://162.55.220.72:5005/object_info_4
req.
GET
name: str
age: int
salary: int

HW_Jmeter_Recorder

Ни в коем случае не делать DDoS атак на сайты!! Это уголовная статья!!

Сделать 1 прогон 1 пользователем.
Открываете любой интернет магазин, и делаете Smoke сценарий пользователя:
1) Открыть главную страницу сайта
2) Открыть страницу каталога
3) Открыть страницу товара
4) Открыть сттраницу корзины.

HW_2

1) http://162.55.220.72:5005/user_info
req. (RAW JSON)
POST
age: int
salary: int
name: str
auth_token

resp.
{'start_qa_salary':salary,
 'qa_salary_after_6_months': salary * 2,
 'qa_salary_after_12_months': salary * 2.9,
 'person': {'u_name':[user_name, salary, age],
                                'u_age':age,
                                'u_salary_1.5_year': salary * 4}
                                }
Действия:
1) Достать из Respose значение из поля 'qa_salary_after_6_months' и передать в поле salary запроса http://162.55.220.72:5005/new_data

2) http://162.55.220.72:5005/new_data
req.
POST
age: int
salary: int
name: str
auth_token

Resp.
{'name':name,
  'age': int(age),
  'salary': [salary, str(salary*2), str(salary*3)]}

Действия:
1) Достать из Respose значение из поля 'name' и передать в поле name запроса http://162.55.220.72:5005/new_data

3) http://162.55.220.72:5005/test_pet_info
req.
POST
age: int
weight: int
name: str
auth_token

Resp.
{'name': name,
 'age': age,
 'daily_food':weight * 0.012,
 'daily_sleep': weight * 2.5}

Тесты:
1) Достать из Respose значение из поля age и передать в поле age запроса http://162.55.220.72:5005/get_test_user

Задание ***
0) Изучать как работают Response Assertion.
1) Сделать Assertion на провекрку статус код 200
2) Сделать Assertion на провекрку 'daily_food':weight * 0.012

4) http://162.55.220.72:5005/get_test_user
req.
POST
age: int
salary: int
name: str
auth_token

Resp.
{'name': name,
 'age':age,
 'salary': salary,
 'family':{'children':[['Alex', 24],['Kate', 12]],
 'u_salary_1.5_year': salary * 4}
  }

Тесты:
Задание ***
0) Изучать как работают Response Assertion.
1) Сделать Assertion на провекрку статус код 200
2) Сделать Assertion на провекрку 'salary': salary
