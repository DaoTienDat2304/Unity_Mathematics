# HƯỚNG DẪN CHI TIẾT BÀI TẬP COORDINATE SYSTEM & WORLD SPACE

## PHẦN A – COORDINATE SYSTEM & WORLD SPACE (20%)

### A1. Tạo Cube tại vị trí (2, 1, 5)

**Các bước thực hiện:**

1. **Mở Unity Editor** và đảm bảo bạn đang ở Scene View
2. **Tạo Cube:**

   - Cách 1: Menu `GameObject` → `3D Object` → `Cube`
   - Cách 2: Click chuột phải trong Hierarchy → `3D Object` → `Cube`
   - Cách 3: Nhấn phím tắt: Trong Hierarchy, click chuột phải → `3D Object` → `Cube`

3. **Đặt vị trí Cube:**

   - Chọn Cube trong Hierarchy
   - Trong Inspector, tìm component `Transform`
   - Đặt các giá trị Position:
     - **X = 2**
     - **Y = 1**
     - **Z = 5**

4. **Kiểm tra:**
   - Cube sẽ xuất hiện ở vị trí (2, 1, 5) trong Scene View
   - Bạn có thể thấy các trục tọa độ tại vị trí này

---

### A2. Bật Gizmos và chụp ảnh các trục

**Các bước thực hiện:**

1. **Bật Gizmos trong Scene View:**

   - Ở góc trên bên phải của Scene View, tìm nút **"Gizmos"**
   - Click vào nút này để bật Gizmos (nút sẽ sáng lên)
   - Hoặc: Menu `Gizmos` ở thanh công cụ Scene View

2. **Hiển thị các trục:**

   - Khi Gizmos được bật, bạn sẽ thấy:
     - **Trục X** (màu đỏ) - hướng sang phải
     - **Trục Y** (màu xanh lá) - hướng lên trên
     - **Trục Z** (màu xanh dương) - hướng về phía bạn (trong Scene View)

3. **Chụp ảnh:**
   - Sử dụng công cụ chụp màn hình (Windows: `Win + Shift + S` hoặc `Print Screen`)
   - Hoặc trong Unity: Menu `Window` → `General` → `Screenshot` (nếu có)
   - Đảm bảo ảnh thể hiện rõ cả 3 trục X, Y, Z

---

### A3. Trả lời câu hỏi

**Câu hỏi 1: Trục nào hướng lên trên trong Unity?**

- **Đáp án: Trục Y**
- Giải thích: Trong Unity, hệ tọa độ sử dụng Y-up, nghĩa là trục Y luôn hướng lên trên (màu xanh lá)

**Câu hỏi 2: Trục nào hướng về phía Camera?**

- **Đáp án: Trục Z**
- Giải thích: Trong Scene View, khi Camera nhìn từ góc mặc định, trục Z hướng về phía Camera (màu xanh dương). Trong World Space, trục Z dương hướng về phía Camera khi Camera ở vị trí âm trên trục Z.

---

## PHẦN B – LEFT-HANDED COORDINATE SYSTEM (15%)

### B1. Xoay Cube với Rotation Y = 90

**Các bước thực hiện:**

1. **Chọn Cube** trong Hierarchy
2. **Trong Inspector**, tìm component `Transform`
3. **Đặt Rotation:**

   - **X = 0**
   - **Y = 90**
   - **Z = 0**

4. **Quan sát:**
   - Cube sẽ quay quanh trục Y một góc 90 độ
   - Quan sát hướng quay của Cube

---

### B2. Trả lời câu hỏi về Left-Handed Coordinate System

**Câu hỏi 1: Cube quay theo chiều nào?**

- **Đáp án:** Cube quay theo chiều **ngược chiều kim đồng hồ** (counter-clockwise) khi nhìn từ trên xuống
- Giải thích: Khi bạn đặt Rotation Y = 90, Cube quay quanh trục Y theo chiều ngược chiều kim đồng hồ

**Câu hỏi 2: Điều này thể hiện Unity sử dụng Left-Handed Coordinate System như thế nào?**

- **Đáp án:**
  - Unity sử dụng **Left-Handed Coordinate System** (hệ tọa độ tay trái)
  - Trong hệ tọa độ này, khi bạn quay quanh một trục dương, vật thể quay theo chiều ngược chiều kim đồng hồ
  - Quy tắc bàn tay trái: Nếu bạn giơ ngón tay cái của bàn tay trái theo hướng trục dương, các ngón tay còn lại sẽ chỉ hướng quay dương
  - Điều này khác với Right-Handed System (như OpenGL) nơi quay theo chiều kim đồng hồ

---

## PHẦN C – LOCAL SPACE VÀ WORLD SPACE (25%)

### C1. Tạo Empty GameObject tên "Parent" tại (5, 0, 0)

**Các bước thực hiện:**

1. **Tạo Empty GameObject:**

   - Menu `GameObject` → `Create Empty`
   - Hoặc: Click chuột phải trong Hierarchy → `Create Empty`

2. **Đổi tên:**

   - Chọn GameObject vừa tạo
   - Trong Inspector, đổi tên từ "GameObject" thành **"Parent"**
   - Hoặc: Click chuột phải vào tên trong Hierarchy → `Rename`

3. **Đặt vị trí:**
   - Chọn Parent trong Hierarchy
   - Trong Inspector, đặt Position:
     - **X = 5**
     - **Y = 0**
     - **Z = 0**

---

### C2. Đặt Cube làm con của Parent và thiết lập Local Position

**Các bước thực hiện:**

1. **Tạo Parent-Child relationship:**

   - **Cách 1 (Drag & Drop):**

     - Trong Hierarchy, kéo thả Cube vào Parent
     - Cube sẽ thụt vào một chút, thể hiện nó là con của Parent

   - **Cách 2 (Inspector):**
     - Chọn Cube
     - Trong Inspector, ở component Transform, kéo Parent từ Hierarchy vào trường "Parent" (nếu có)
     - Hoặc: Click chuột phải vào Cube → `Change Parent` → chọn Parent

2. **Thiết lập Local Position:**

   - Đảm bảo Cube đã là con của Parent
   - Chọn Cube trong Hierarchy
   - Trong Inspector, component Transform sẽ hiển thị **Local Position**
   - Đặt Local Position:
     - **X = 0**
     - **Y = 2**
     - **Z = 0**

3. **Quan sát:**
   - Cube sẽ xuất hiện ở vị trí (5, 2, 0) trong World Space
   - Nhưng Local Position của nó là (0, 2, 0) so với Parent

---

### C3. Ghi lại Local Position và World Position

**Các bước thực hiện:**

1. **Xem Local Position:**

   - Chọn Cube trong Hierarchy
   - Trong Inspector, component Transform hiển thị:
     - **Position** (đây là Local Position khi có parent)
     - Ghi lại: **Local Position = (0, 2, 0)**

2. **Xem World Position:**
   - Vẫn chọn Cube
   - Trong Inspector, ở component Transform:
     - Click vào biểu tượng **3 chấm ngang** (⋮) ở góc trên bên phải của Transform
     - Chọn **"World"** từ menu dropdown
     - Hoặc: Trong Scene View, khi chọn Cube, bạn sẽ thấy World Position trong Gizmo
   - Ghi lại: **World Position = (5, 2, 0)**

**Giải thích:**

- Local Position: Vị trí của Cube so với Parent (0, 2, 0)
- World Position: Vị trí của Cube trong không gian thế giới = Parent Position + Local Position = (5, 0, 0) + (0, 2, 0) = (5, 2, 0)

---

### C4. Di chuyển Parent và quan sát

**Các bước thực hiện:**

1. **Di chuyển Parent:**

   - Chọn **Parent** trong Hierarchy (KHÔNG phải Cube)
   - Trong Inspector, đặt Position:
     - **X = 8**
     - **Y = 0**
     - **Z = 0**

2. **Quan sát và ghi lại:**

   **Câu hỏi 1: Local Position của Cube có thay đổi không?**

   - **Đáp án: KHÔNG**
   - Giải thích: Local Position của Cube vẫn là (0, 2, 0) vì nó là vị trí tương đối so với Parent, không phụ thuộc vào vị trí của Parent trong World Space

   **Câu hỏi 2: World Position của Cube thay đổi như thế nào?**

   - **Đáp án:** World Position thay đổi từ (5, 2, 0) thành **(8, 2, 0)**
   - Giải thích:
     - World Position = Parent World Position + Cube Local Position
     - Khi Parent di chuyển từ (5, 0, 0) sang (8, 0, 0), World Position của Cube = (8, 0, 0) + (0, 2, 0) = (8, 2, 0)
     - Cube di chuyển cùng với Parent vì nó là con của Parent

---

## PHẦN D – GRAPHICS PIPELINE (20%)

### D1. Di chuyển Camera dọc trục Z từ -10 đến -3

**Các bước thực hiện:**

1. **Chọn Main Camera:**

   - Trong Hierarchy, tìm và chọn **Main Camera**

2. **Di chuyển Camera:**

   - Trong Inspector, component Transform
   - Thay đổi Position Z từ **-10** thành **-3**
   - Giữ nguyên X và Y

3. **Quan sát:**
   - Trong Scene View hoặc Game View, bạn sẽ thấy Cube trông **to hơn**
   - Camera đã tiến gần hơn đến Cube

---

### D2. Thay đổi các thông số Camera

**Các bước thực hiện:**

1. **Thay đổi Field of View (FOV):**

   - Vẫn chọn Main Camera
   - Trong Inspector, tìm component `Camera`
   - Tìm trường **Field of View**
   - Thử các giá trị khác nhau:
     - **FOV nhỏ hơn (ví dụ: 30):** Object trông to hơn, góc nhìn hẹp hơn
     - **FOV lớn hơn (ví dụ: 90):** Object trông nhỏ hơn, góc nhìn rộng hơn
   - Quan sát sự thay đổi trong Game View

2. **Thay đổi Near Clip Plane:**
   - Trong component Camera, tìm **Near**
   - Thử các giá trị:
     - **Near lớn hơn (ví dụ: 5):** Object có thể biến mất nếu quá gần Camera
     - **Near nhỏ hơn (ví dụ: 0.1):** Object gần Camera vẫn hiển thị
   - Quan sát sự thay đổi

---

### D3. Trả lời câu hỏi

**Câu hỏi 1: Vì sao object trông to hoặc nhỏ hơn dù không đổi vị trí?**

**Đáp án:**

- **Khoảng cách từ Camera:** Khi Camera di chuyển gần hơn (Z từ -10 đến -3), object trông to hơn vì khoảng cách giảm. Đây là hiệu ứng perspective (phối cảnh).
- **Field of View (FOV):**
  - FOV nhỏ → góc nhìn hẹp → object trông to hơn (như ống nhòm)
  - FOV lớn → góc nhìn rộng → object trông nhỏ hơn (như mắt cá)
- **Perspective Projection:** Unity sử dụng phép chiếu phối cảnh, nơi các object gần Camera trông to hơn và xa hơn trông nhỏ hơn.

**Câu hỏi 2: Vì sao object có thể biến mất khỏi màn hình?**

**Đáp án:**

- **Near Clip Plane:** Object nằm gần Camera hơn giá trị Near sẽ bị cắt và không hiển thị. Đây là giới hạn gần nhất mà Camera có thể nhìn thấy.
- **Far Clip Plane:** Object nằm xa Camera hơn giá trị Far sẽ bị cắt và không hiển thị. Đây là giới hạn xa nhất mà Camera có thể nhìn thấy.
- **Frustum Culling:** Unity chỉ render các object nằm trong vùng nhìn thấy (view frustum) của Camera. Object ngoài vùng này sẽ không được render.
- **Viewport:** Object có thể nằm ngoài vùng hiển thị của màn hình (viewport) nên không thấy được.

---

## PHẦN E – SCREEN SPACE (20%)

### E1. Tạo script WorldToScreen.cs

**Lưu ý:** Script này đã có sẵn trong project tại `Assets/WorldToScreen.cs`

**Nội dung script:**

```csharp
using UnityEngine;

public class WorldToScreen : MonoBehaviour
{
    void Update()
    {
        Vector3 screenPos =
            Camera.main.WorldToScreenPoint(transform.position);

        Debug.Log(screenPos);
    }
}
```

**Nếu cần tạo mới:**

1. Trong Project window, click chuột phải vào thư mục `Assets`
2. Chọn `Create` → `C# Script`
3. Đặt tên: `WorldToScreen`
4. Mở script và copy nội dung trên vào

---

### E2. Gắn script vào Cube và chạy game

**Các bước thực hiện:**

1. **Gắn script vào Cube:**

   - Chọn **Cube** trong Hierarchy
   - Trong Inspector, click nút **"Add Component"**
   - Tìm và chọn **"World To Screen"** (hoặc gõ "WorldToScreen")
   - Hoặc: Kéo thả script `WorldToScreen.cs` từ Project window vào Cube trong Hierarchy

2. **Chạy game:**

   - Click nút **Play** (▶) ở thanh công cụ trên cùng
   - Hoặc nhấn phím tắt: **Ctrl + P** (Windows) hoặc **Cmd + P** (Mac)

3. **Xem kết quả:**
   - Mở **Console** window: Menu `Window` → `General` → `Console`
   - Hoặc nhấn **Ctrl + Shift + C**
   - Bạn sẽ thấy các giá trị Screen Position được in ra liên tục trong Console

---

### E3. Ghi lại Screen Position

**Các bước thực hiện:**

1. **Screen Position khi Cube ở giữa màn hình:**

   - Đảm bảo Cube nằm ở giữa Game View
   - Di chuyển Camera hoặc Cube để Cube xuất hiện ở giữa màn hình
   - Xem giá trị trong Console
   - **Ghi lại:** Screen Position ≈ **(Screen.width/2, Screen.height/2, distance)**
     - Ví dụ: Nếu màn hình 1920x1080, giá trị sẽ khoảng (960, 540, ...)

2. **Screen Position khi Cube ở góc dưới bên trái:**
   - Di chuyển Cube hoặc Camera để Cube xuất hiện ở góc dưới bên trái của Game View
   - Xem giá trị trong Console
   - **Ghi lại:** Screen Position ≈ **(small X, small Y, distance)**
     - Ví dụ: (100, 50, ...) hoặc giá trị tương tự

**Lưu ý:**

- Giá trị X và Y trong Screen Space tính bằng pixel
- Giá trị Z là khoảng cách từ Camera đến object (trong World Space)

---

### E4. Trả lời câu hỏi

**Câu hỏi 1: Gốc tọa độ của Screen Space nằm ở đâu?**

**Đáp án:**

- **Gốc tọa độ (0, 0) nằm ở góc dưới bên trái** của màn hình
- **Trục X:** Tăng từ trái sang phải (0 → Screen.width)
- **Trục Y:** Tăng từ dưới lên trên (0 → Screen.height)
- **Trục Z:** Khoảng cách từ Camera đến object (trong World Space)

**Giải thích:**

- Unity sử dụng hệ tọa độ Screen Space với gốc ở góc dưới bên trái
- Điều này khác với một số hệ thống khác (như Windows API) sử dụng gốc ở góc trên bên trái

---

**Câu hỏi 2: Screen Space khác World Space như thế nào?**

**Đáp án:**

**World Space (Không gian thế giới):**

- Là hệ tọa độ 3D tuyệt đối trong scene
- Gốc tọa độ (0, 0, 0) là điểm gốc của scene
- Đơn vị: Unity units (thường là mét)
- Tọa độ không đổi khi Camera di chuyển
- Sử dụng để định vị các object trong scene

**Screen Space (Không gian màn hình):**

- Là hệ tọa độ 2D trên màn hình hiển thị
- Gốc tọa độ (0, 0) ở góc dưới bên trái màn hình
- Đơn vị: Pixel
- Tọa độ thay đổi khi Camera di chuyển hoặc xoay
- Sử dụng để định vị UI elements, hiển thị text trên màn hình

**Sự khác biệt chính:**

1. **Chiều:** World Space là 3D, Screen Space là 2D
2. **Đơn vị:** World Space dùng Unity units, Screen Space dùng pixels
3. **Gốc tọa độ:** World Space có gốc ở (0, 0, 0) của scene, Screen Space có gốc ở góc dưới trái màn hình
4. **Tính tương đối:** World Space là tuyệt đối, Screen Space phụ thuộc vào Camera và viewport
5. **Mục đích:** World Space cho object trong scene, Screen Space cho UI và hiển thị trên màn hình

**Chuyển đổi:**

- `Camera.WorldToScreenPoint()`: Chuyển từ World Space sang Screen Space
- `Camera.ScreenToWorldPoint()`: Chuyển từ Screen Space sang World Space

---

## TIPS VÀ LƯU Ý

1. **Scene View vs Game View:**

   - Scene View: Để chỉnh sửa scene
   - Game View: Để xem kết quả khi chạy game (nhấn Play)

2. **Gizmos:**

   - Luôn bật Gizmos để thấy các trục tọa độ
   - Có thể tắt/bật trong Scene View

3. **Transform Modes:**

   - Local vs World: Click vào biểu tượng 3 chấm (⋮) trong Transform để chuyển đổi

4. **Console Window:**

   - Luôn mở Console để xem Debug.Log()
   - Có thể clear console bằng nút Clear

5. **Camera:**
   - Main Camera mặc định ở vị trí (0, 1, -10)
   - Có thể di chuyển Camera trong Scene View để quan sát tốt hơn

---

## KẾT LUẬN

Bài tập này giúp bạn hiểu:

- ✅ Hệ tọa độ trong Unity (X, Y, Z)
- ✅ Left-Handed Coordinate System
- ✅ Sự khác biệt giữa Local Space và World Space
- ✅ Graphics Pipeline và Camera settings
- ✅ Chuyển đổi giữa World Space và Screen Space

Chúc bạn hoàn thành tốt bài tập! 🎮
