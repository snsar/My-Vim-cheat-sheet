# Vim Cheat Sheet

## 📋 Mục lục
- [Di chuyển theo trục dọc](#di-chuyển-theo-trục-dọc)
- [Di chuyển theo trục ngang](#di-chuyển-theo-trục-ngang)
- [Tìm kí tự](#tìm-kí-tự)
- [Operator](#operator)
- [Text Objects](#text-objects)
- [Registers](#registers)
- [Buffers](#buffers)
- [Cửa sổ và tab](#cửa-sổ-và-tab)
- [Các lệnh chỉnh sửa](#các-lệnh-chỉnh-sửa)
- [Các chế độ trong Vim](#các-chế-độ-trong-vim)

## Di chuyển theo trục dọc
- `j` → xuống 👇
- `k` → lên ☝
- `{` → di chuyển lên paragraph trước đó
- `}` → di chuyển xuống paragraph tiếp theo
- `Ctrl + d` → di chuyển màn hình xuống nửa trang
- `Ctrl + u` → di chuyển màn hình lên nửa trang
- `Ctrl + f` → di chuyển xuống một trang đầy đủ
- `Ctrl + b` → di chuyển lên một trang đầy đủ
- `[số] + j/k` → di chuyển lên/xuống [số] dòng
- `Ctrl + e` → cuộn văn bản xuống (giữ con trỏ)
- `Ctrl + y` → cuộn văn bản lên (giữ con trỏ)
- `zt` → đặt dòng hiện tại lên trên cùng màn hình
- `zb` → đặt dòng hiện tại xuống cuối màn hình
- `zz` → đặt dòng hiện tại vào giữa màn hình
- `gg` → nhảy lên đầu file
- `G` → nhảy xuống cuối file
- `:[số]` hoặc `[số]G` → nhảy đến dòng số [số]
- `Shift + h` (hoặc `H`) → nhảy lên đầu màn hình không cuộn
- `Shift + l` (hoặc `L`) → nhảy xuống cuối màn hình không cuộn
- `Shift + m` (hoặc `M`) → nhảy đến giữa màn hình

## Di chuyển theo trục ngang
- `h` → sang trái
- `l` → sang phải
- `w` → di chuyển tới đầu từ tiếp theo (kí tự đặc biệt tính là một từ riêng)
- `W` → di chuyển tới đầu từ tiếp theo (bỏ qua dấu câu)
- `b` → di chuyển tới đầu từ trước đó
- `B` → di chuyển tới đầu từ trước đó (bỏ qua dấu câu)
- `e` → di chuyển tới cuối từ hiện tại
- `E` → di chuyển tới cuối từ hiện tại (bỏ qua dấu câu)
- `ge` → di chuyển tới cuối từ trước đó
- `gE` → di chuyển tới cuối từ trước đó (bỏ qua dấu câu)
- `0` → nhảy đến đầu dòng (cột 0)
- `^` hoặc `0w` → nhảy đến kí tự đầu tiên của dòng
- `$` → di chuyển đến cuối dòng (bao gồm khoảng trắng)
- `g_` → di chuyển đến kí tự cuối cùng của dòng (không tính khoảng trắng)

## Tìm kí tự
- `f + <kí tự>` → tìm kí tự tiếp theo trên dòng hiện tại (từ trái sang phải)
- `F + <kí tự>` → tìm kí tự trước đó trên dòng hiện tại (từ phải sang trái)
- `t + <kí tự>` → di chuyển đến vị trí trước kí tự tiếp theo trên dòng
- `T + <kí tự>` → di chuyển đến vị trí sau kí tự trước đó trên dòng
- `;` → lặp lại lệnh tìm kiếm theo hướng ban đầu
- `,` → lặp lại lệnh tìm kiếm theo hướng ngược lại
- `/pattern` → tìm kiếm "pattern" trong file (hướng xuống)
- `?pattern` → tìm kiếm "pattern" trong file (hướng lên)
- `n` → đi đến kết quả tìm kiếm tiếp theo
- `N` → đi đến kết quả tìm kiếm trước đó
- `*` → tìm từ dưới con trỏ trong hướng xuống
- `#` → tìm từ dưới con trỏ trong hướng lên

## Operator
- `d` → delete (xóa)
- `c` → change (thay đổi)
- `y` → yank (sao chép)
- `v` → visual select (chọn)
- `p` → put/paste (dán)
- `>` → indent (thụt lề phải)
- `<` → outdent (thụt lề trái)
- `=` → auto format (định dạng tự động)
- `gu` → chuyển thành chữ thường
- `gU` → chuyển thành chữ hoa
- `g~` → đảo ngược chữ hoa/thường

## Text Objects
**Phạm vi:**
- `w` → word (từ)
- `s` → sentence (câu)
- `p` → paragraph (đoạn văn)
- `t` → tag (thẻ HTML/XML)
- `[` hoặc `]` → khối trong ngoặc vuông
- `(` hoặc `)` → khối trong ngoặc tròn
- `{` hoặc `}` → khối trong ngoặc nhọn
- `'` → khối trong dấu nháy đơn
- `"` → khối trong dấu nháy kép
- `` ` `` → khối trong backtick

**Loại phạm vi:**
- `a` → around (xung quanh, bao gồm dấu ngoặc/khoảng trắng)
- `i` → inside (bên trong, không bao gồm dấu ngoặc/khoảng trắng)

**Ví dụ kết hợp:**
- `diw` → xóa từ hiện tại
- `ciw` → thay đổi từ hiện tại
- `yi"` → sao chép nội dung trong dấu nháy kép
- `va{` → chọn một khối code trong ngoặc nhọn (bao gồm dấu ngoặc)
- `dt=` → xóa từ vị trí hiện tại đến trước dấu bằng
- `df=` → xóa từ vị trí hiện tại đến và bao gồm dấu bằng

> 📝 **Công thức tổng quát:** `Operator + [số lần lặp] + Motion/TextObject`

## Registers
Vim có nhiều loại register để lưu trữ văn bản:

- `""` → Unnamed register (register mặc định khi xóa/sao chép)
- `"0` - `"9` → Numbered registers (10 register đánh số tự động)
- `"a` - `"z` → Named registers (26 register có thể đặt tên)
- `"+` hoặc `"*` → Clipboard register (kết nối với clipboard hệ thống)
- `"_` → Black hole register (ném nội dung vào "hố đen", không lưu trữ)
- `"%` → Current filename register
- `".` → Last inserted text register
- `":` → Last command register
- `"/` → Last search pattern register

**Xem tất cả registers:**
```
:reg    # hiển thị tất cả registers
:reg a  # hiển thị nội dung của register a
```

**Ví dụ sử dụng:**
- `"ayy` → sao chép dòng hiện tại vào register a
- `"ap` → dán nội dung từ register a
- `"+y` → sao chép vào clipboard hệ thống
- `"+p` → dán từ clipboard hệ thống
- `"_dd` → xóa dòng mà không lưu vào register nào

> 📝 **Công thức:** `"[register][operator][motion]`

## Buffers
Vim sử dụng buffer để quản lý nhiều file cùng lúc.

**Các lệnh quản lý buffer:**
- `:ls` hoặc `:buffers` → liệt kê tất cả buffer
- `:badd [file]` → thêm file vào buffer
- `:bn` hoặc `:bnext` → đi đến buffer tiếp theo
- `:bp` hoặc `:bprevious` → đi đến buffer trước đó
- `:bf` hoặc `:bfirst` → đi đến buffer đầu tiên
- `:bl` hoặc `:blast` → đi đến buffer cuối cùng
- `:b [số]` hoặc `:buffer [số]` → đi đến buffer có số tương ứng
- `:b [tên]` → đi đến buffer có tên tương ứng (gõ một phần cũng được)
- `:bd` hoặc `:bdelete` → xóa buffer hiện tại
- `:bd [số]` → xóa buffer có số tương ứng
- `:bufdo [lệnh]` → thực hiện lệnh trên tất cả buffer

## Cửa sổ và tab
**Chia cửa sổ:**
- `:sp [file]` hoặc `:split [file]` → chia cửa sổ ngang
- `:vs [file]` hoặc `:vsplit [file]` → chia cửa sổ dọc
- `Ctrl + w + h/j/k/l` → di chuyển giữa các cửa sổ
- `Ctrl + w + H/J/K/L` → di chuyển cửa sổ hiện tại
- `Ctrl + w + +/-` → tăng/giảm kích thước cửa sổ ngang
- `Ctrl + w + >/< ` → tăng/giảm kích thước cửa sổ dọc
- `Ctrl + w + =` → cân bằng kích thước tất cả cửa sổ
- `:q` → đóng cửa sổ hiện tại

**Tab:**
- `:tabnew [file]` → mở file trong tab mới
- `:tabc` → đóng tab hiện tại
- `:tabo` → đóng tất cả tab khác
- `:tabn` hoặc `gt` → đi đến tab tiếp theo
- `:tabp` hoặc `gT` → đi đến tab trước đó
- `[số]gt` → đi đến tab số [số]

## Các lệnh chỉnh sửa
- `i` → insert mode trước con trỏ
- `I` → insert mode ở đầu dòng
- `a` → insert mode sau con trỏ
- `A` → insert mode ở cuối dòng
- `o` → mở dòng mới bên dưới và vào insert mode
- `O` → mở dòng mới bên trên và vào insert mode
- `x` → xóa kí tự dưới con trỏ
- `X` → xóa kí tự trước con trỏ
- `dd` → xóa dòng hiện tại
- `D` → xóa từ vị trí con trỏ đến cuối dòng
- `cc` → thay đổi dòng hiện tại
- `C` → thay đổi từ vị trí con trỏ đến cuối dòng
- `r` → thay thế kí tự
- `R` → replace mode (ghi đè)
- `J` → nối dòng hiện tại với dòng dưới
- `~` → đảo chữ hoa/thường của kí tự dưới con trỏ
- `u` → undo
- `Ctrl + r` → redo
- `.` → lặp lại lệnh cuối cùng

## Các chế độ trong Vim
- **Normal Mode** → chế độ mặc định, dùng để di chuyển và thực hiện lệnh
- **Insert Mode** → chế độ nhập văn bản (`i`, `I`, `a`, `A`, `o`, `O`)
- **Visual Mode** → chế độ chọn văn bản (`v`, `V`, `Ctrl + v`)
- **Command Mode** → chế độ nhập lệnh (`:`)
- **Replace Mode** → chế độ thay thế (`R`)
- **Ex Mode** → chế độ mở rộng của Command Mode (`Q`)

---

> 💡 **Mẹo:** Sử dụng `:help [lệnh]` để xem hướng dẫn chi tiết về bất kỳ lệnh nào trong Vim.
