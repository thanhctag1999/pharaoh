# Danh sách asset cần tạo thêm

Game hiện dựng kiến trúc bằng Canvas 2.5D để chạy ngay mà không cần tải thư viện hoặc model ngoài. Các asset dưới đây có thể thay dần các khối Canvas để đạt chất lượng gần ảnh design hơn.

## Quy chuẩn chung

- Phong cách: Egyptian chibi, 3D cartoon, màu cát vàng, điểm nhấn xanh turquoise và vàng kim.
- Camera: orthographic 3/4 top-down, nhìn từ trên xuống khoảng 55–60 độ.
- Ánh sáng: nắng ấm từ góc trên trái; bóng đổ mềm về phía dưới phải.
- File: PNG hoặc WebP nền trong suốt; background và floor dùng WebP/JPG.
- Neo vật thể: bottom-center để dễ đặt và sắp xếp theo trục Y.
- Không vẽ UI, chữ, nhân vật hoặc vật thể khác dính vào asset kiến trúc.
- Bản 1x tối thiểu; nên xuất thêm bản 2x cho màn hình Retina.

## Ưu tiên 1 — bộ map chính

| File đề xuất | Kích thước 2x | Nội dung |
|---|---:|---|
| `arena-floor-sandstone.webp` | 1024×2048 | Nền sân lát đá liền mạch, có khe đá và cát phủ nhẹ |
| `desert-skyline.webp` | 1024×512 | Bầu trời, núi cát và các kim tự tháp xa; không có foreground |
| `wall-straight.png` | 512×256 | Đoạn tường sa thạch thẳng, viền turquoise, dài khoảng 4 block |
| `wall-short.png` | 256×256 | Đoạn tường thấp 1–2 block dùng tạo mê cung |
| `wall-corner-left.png` | 384×384 | Góc tường chữ L quay trái |
| `wall-corner-right.png` | 384×384 | Góc tường chữ L quay phải |
| `wall-broken.png` | 512×320 | Tường vỡ, có gạch vụn nhưng silhouette va chạm rõ |
| `temple-gate.png` | 768×640 | Cổng đền trung tâm, hai trụ, đĩa mặt trời và cánh Scarab |
| `obelisk-large.png` | 320×720 | Obelisk cao có chữ tượng hình và chân đế xanh-vàng |
| `pyramid-small.png` | 384×320 | Kim tự tháp nhỏ dùng làm vật cản trong sân |
| `temple-column.png` | 256×480 | Cột đền độc lập, chân đế vuông và đầu cột trang trí |

## Ưu tiên 2 — cảnh quan và vật trang trí

| File đề xuất | Kích thước 2x | Nội dung |
|---|---:|---|
| `palm-tree-a.png` | 384×640 | Cây chà là cao, tán lệch trái |
| `palm-tree-b.png` | 384×640 | Biến thể tán lệch phải để tránh lặp |
| `brazier-fire.png` | 320×420 | Lư đồng xanh-vàng và lửa thần Ra |
| `sarcophagus.png` | 320×480 | Quan tài Pharaoh dùng chứa item |
| `treasure-chest.png` | 320×240 | Rương cổ vật mở/đóng; nên xuất hai frame |
| `pottery-set.png` | 384×256 | Cụm bình gốm có thể phá vỡ |
| `rubble-a.png` | 256×180 | Đá vụn nhỏ, không cản đường |
| `rubble-b.png` | 256×180 | Biến thể đá vụn và cỏ sa mạc |
| `water-pool.png` | 512×320 | Hồ nước nông với viền đá và cây cọ nhỏ |
| `scarab-pedestal.png` | 320×380 | Bệ đá đặt item Scarab phát sáng |

## Ưu tiên 3 — bẫy và vật thể tương tác

| File đề xuất | Kích thước 2x | Nội dung |
|---|---:|---|
| `trap-spikes-off.png` | 320×240 | Sàn gai ở trạng thái cảnh báo |
| `trap-spikes-on.png` | 320×240 | Sàn gai đã bật, giữ nguyên footprint với bản off |
| `trap-fire-statue.png` | 320×480 | Tượng thần phun lửa, không kèm tia lửa dài |
| `trap-arrow-wall.png` | 512×300 | Tường bắn tên có lỗ bắn dễ nhận biết |
| `trap-crusher-door.png` | 512×640 | Cửa đá nghiền, gồm hai trạng thái mở/đóng |
| `boulder.png` | 256×256 | Đá lăn tròn, texture dễ nhận ra khi xoay |
| `quicksand.webp` | 384×256 | Cát lún dạng sprite sheet 6–8 frame |
| `collapse-hole.png` | 384×288 | Hố sụp với viền nứt rõ ràng |

## Sprite nhân vật và hiệu ứng nên nâng cấp

- `pharaoh`, `bastet`, `anubis`, `mummy`, `scarab`: PNG/WebP 512×704, nền trong suốt, cùng scale và điểm neo.
- Mỗi nhân vật nên có tối thiểu: idle 6 frame, run 8 frame, melee 6 frame, throw 6 frame, dash 4 frame, eliminated 6 frame.
- Vũ khí: 256×256, tâm xoay nằm đúng giữa canvas.
- Vệt boomerang, chém, băng, lửa, hồi sinh và teleport: sprite sheet 512×512 hoặc 1024×1024.

## Asset có thể dùng nếu chuyển sang Three.js

- `arena-kit.glb`: modular wall, corner, gate, column, pyramid, obelisk và pedestal dùng chung material atlas.
- `desert-props.glb`: palm, pottery, rubble, chest, brazier và sarcophagus.
- `egypt-materials.webp`: atlas 2048×2048 gồm sandstone, turquoise enamel, gold và dark stone.
- Mỗi mesh tĩnh nên dưới 5.000 triangles; toàn cảnh mobile nên dưới khoảng 120.000 triangles và dùng chung material khi có thể.
- Pivot của model đặt ở giữa đáy; đơn vị 1 mét; trục Y hướng lên; ánh sáng/bóng đổ không bake quá đậm.

## Thứ tự sản xuất đề xuất

1. Floor, skyline, wall thẳng, wall góc và cổng đền.
2. Obelisk, kim tự tháp nhỏ, cột và cây cọ.
3. Bộ bẫy đầy đủ.
4. Rương, bình, quan tài, bệ item và đá vụn.
5. Nâng cấp sprite nhân vật và effect animation.
