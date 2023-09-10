## :point_right: Table of content
- [Di chuyển theo trục dọc](#point_right-di-chuyển-theo-trục-dọc)
- [Di chuyển theo trục ngang](#point_right-di-chuyển-theo-trục-ngang)
- [Tìm kí tự](#point_right-tìm-kí-tự)
- [Operator](#point_right-tìm-kí-tự)
- [Text Objects](#point_right-text-objects)
- [Registers](#-registers-)
## :point_right: Di chuyển theo trục dọc:

- j ->  xuống 👇
- k -> lên ☝
- { : di chuyển lên paragraph
- } : xuống ...
- Ctrl + d : di chuyển màn xuống
- Ctrl + u: di chuyển màn lên
- number + [j or k]
- Ctrl + e: scroll text chuyển xuống
- Ctrl + y: scroll text chuyển lên
- zt: di con trỏ hiện tại lên trên cùng
- zb : di con trỏ hiện tại xuống cuối cùng
- zz : di con trỏ vào hiện tại ra giữa màn
- gg: lên đầu file
- G: xuống cuối file
- Shift + h : lên đầu ko scroll text
- Shift + l : xuồng cuối ko scroll text
- Shift + m

## :point_right: Di chuyển theo trục ngang:
- h : sang trái
- l: sang phải
- w: di chuyển theo từ sang phải(các kí tự đặc biệt cũng tính là 1 từ)
- W: di chuyển theo từ
- b: di chuyển sang trái
- B: ... bao gồm kí tự đặc biệt
- e: di chuyển sang trái đến cuối từ đó
- E: .... bao gồm đặc biệt
- ge: di chuyển sang trái đến kết thúc của từ trước đó
- 0 : nhảy đến đầu dòng <ko phải kí tự>
- shift + 6( ^) hoặc 0 + w : nhảy đến kí tự đầu dòng là kí tự
- $ hoặc g_ : di chuyển đến cuối dòng

## :point_right: Tìm kí tự:
- f + <kí tự> : tìm kí tự theo chiều trái sang phải (dùng ; để lặp lại hành động hoặc .)
- F + <kí tự> : tìm từ F theo hướng ngược lại
- t + <kí tự> : tìm theo chiều trái sang phải kí tự ở phía trước 
- T + <kí tự> : tìm theo chiều ngược lại ở kí tự đứng trước

## :point_right: Operator 
- d : delete
- c : change
- v : select
- y : copy
- p : paste

##  :point_right: Text Objects
- w : word (1 từ)
- s : sentence (1 câu)
- p : paragraph (đoạn văn)
- t : tag (thường dùng trong html)
---
- a : around
- i : inside ( bên trong)
---
- i" : inside double quote
- i' : inside single quote
- i` : inside backtick
- i( hoặc ib : inside singe (
- i{ hoặc iB : inside {
- iw : inside word
- is : insside sentence
- ip : inside paragraph
- Tương tự cho a ( a", a', a`, a(, a{ ) 
---
Example: 
- dw : delete word 
- diw : delte in word
- cw, ciw
- dt= : xoá đến trước dấu bằng tiếp theo
- df= : xoá đến dấu bằng tiếp theo

> Công thức : Operator + number(optional) + motion (text object) 🎃

## 👉 Registers 
> 1. There are many register:
> 2. command to show all register :reg
- "" : unnameed register (when use delete command d or yank command y save to unnamed register)  
- "+ hoặc "* : register này có thể dùng khi copy và select text ra bên ngoài
- Example: khi sao chép ở chrome sau đó vào vim ta dùng lệnh "+p hoặc "*p để paste hoặc ngược lại copy trong vim bằng lệnh "+y hoặc "*y
- "_ : Black hole register. Ví dụ khi không muốn text đã xoá lưu vào unnamed register ta có thể dùng lệnh "_d
- Ngoài ra còn có number register là các kí tự được copy gần nhất từ 0->9 là "0, "1, ..., "9
- Còn có Register tự định nghĩa là "a -> "z
- Còn nhiều register sẽ cập nhật sau ...

> Công thức: Register + textObject 👌

##  