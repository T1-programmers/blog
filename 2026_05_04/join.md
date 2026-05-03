### Join이란?

Join은 **두 개 이상의 테이블을 특정 조건에 따라 묶어서 하나의 테이블로 보여주는 것**입니다.

_Inner Join_, _Left Outer Join_, _Right Outer Join_, *Full Outer Join*이 있습니다.

<img width="2320" height="562" alt="image" src="https://github.com/user-attachments/assets/677a9976-dc84-4706-9526-96c2beaf0f63" />

**예시 테이블**

<img width="1334" height="502" alt="image" src="https://github.com/user-attachments/assets/4798b074-eb43-4e6f-a850-d3c815037b86" /><br />

### 1. Inner Join

Inner Join은 **조건을 만족하는 행만**을 결과값으로 보여줍니다.<br /><br />

```sql
SELECT * FROM taste A INNER JOIN food_color B ON A.favorite_food = B.food
```

<img width="1398" height="220" alt="image" src="https://github.com/user-attachments/assets/125d85bb-c011-4905-8eaa-f84d45d21183" /><br />

### 2. Left Outer Join

Left Outer Join은 **왼쪽 테이블의 행은 모두 포함**시키고 **오른쪽 테이블은 조건을 만족하는 행만 포함**시키는 방식입니다.

조건을 만족하지 않는 행의 칼럼은 모두 NULL을 반환합니다.<br /><br />

```sql
SELECT * FROM taste A LEFT OUTER JOIN food_color B ON A.favorite_food = B.food
```

<img width="1388" height="294" alt="image" src="https://github.com/user-attachments/assets/e441191f-8d23-454b-a3a2-88292cf019e5" /><br />

### 3. Right Outer Join

Right Outer Join은 **오른쪽 테이블의 행은 모두 포함**시키고 **왼쪽 테이블은 조건을 만족하는 행만 포함**시키는 방식입니다. (Left Outer Join의 반대 방향 버전)

조건을 만족하지 않는 행의 칼럼은 모두 NULL을 반환합니다.<br /><br />

```sql
SELECT * FROM taste A RIGHT OUTER JOIN food_color B ON A.favorite_food = B.food
```

<img width="1400" height="362" alt="image" src="https://github.com/user-attachments/assets/a50229e1-9d0a-418a-9fd6-def4850ef236" /><br />

### 4. Full Outer Join

Full Outer Join은 **모든 테이블의 행을 포함**시키는 방식입니다.

조건을 만족하지 않는 행의 칼럼은 모두 NULL을 반환합니다.<br /><br />

```sql
SELECT * FROM taste A FULL OUTER JOIN food_color B ON A.favorite_food = B.food
```

<img width="1396" height="434" alt="image" src="https://github.com/user-attachments/assets/1c5179ab-aaf0-4c53-adca-9601ca7602a6" />
