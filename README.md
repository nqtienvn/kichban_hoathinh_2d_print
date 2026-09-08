# Video quảng cáo 2D V3

Skill `video-quang-cao-v3` tạo kịch bản kể chuyện tiếng Việt, bộ prompt video AI theo lô và bảng nhịp dựng cho quảng cáo sản phẩm. Phong cách giữ chuyển động nhân vật, zoom theo hành động, thay đổi bố cục và ô phóng đại theo bộ V3 đã được kiểm chứng với video HARUCO.

## Nội dung

Skill nằm tại `.agents/skills/video-quang-cao-v3/` theo cấu trúc Agent Skills mở:

- `SKILL.md`: hướng dẫn chính.
- `references/nhip-v3.md`: nhịp chuyển động, công thức câu chuyện và phân bổ thời lượng.
- `references/haruco-v3-approved.txt`: 10 prompt V3 đã được duyệt làm mẫu phong cách.
- `assets/nhan-vat-v3.png`: ảnh nhân vật vàng tham chiếu.
- `agents/openai.yaml`: tên và mô tả hiển thị trong Codex.

Skill không chứa khóa API, thông tin đăng nhập hoặc dữ liệu riêng tư. Ảnh sản phẩm mới phải được người dùng cung cấp ở mỗi lần làm video để giữ đúng hình dạng và tính năng.

## Dùng trong repo này

Mở Codex hoặc Gemini CLI từ thư mục gốc repo. Hai công cụ có thể quét `.agents/skills` ở cấp repo.

Trong Codex, gọi trực tiếp:

```text
$video-quang-cao-v3
Sản phẩm: [tên và mã]
Công dụng/đặc điểm đúng mẫu: [danh sách]
Thời lượng video: 60 giây
```

Trong Gemini CLI, kiểm tra skill bằng `/skills list`, dùng `/skills reload` nếu vừa kéo code mới, rồi yêu cầu bằng ngôn ngữ tự nhiên; agent sẽ kích hoạt skill khi mô tả khớp. Có thể cài ở phạm vi người dùng bằng lệnh `gemini skills install <đường-dẫn-tới-.agents/skills/video-quang-cao-v3>` sau khi clone repo.

Trong Claude Code, chép thư mục skill vào `~/.claude/skills/video-quang-cao-v3/`, sau đó gọi `/video-quang-cao-v3` hoặc yêu cầu tạo quảng cáo theo phong cách V3. Claude Code cũng tự phát hiện skill dự án nếu thư mục được đặt tại `.claude/skills/video-quang-cao-v3/`.

## Cài dùng cho mọi repo trên Windows

Lệnh PowerShell sau tải repo và cài cùng một skill vào các vị trí người dùng phổ biến:

```powershell
$repo = "$env:USERPROFILE\Documents\GitHub\kichban_hoathinh_2d_print"
if (-not (Test-Path $repo)) { git clone https://github.com/nqtienvn/kichban_hoathinh_2d_print.git $repo }
$source = "$repo\.agents\skills\video-quang-cao-v3"
$targets = @(
  "$env:USERPROFILE\.agents\skills\video-quang-cao-v3", # Codex/Gemini Agent Skills alias
  "$env:USERPROFILE\.codex\skills\video-quang-cao-v3",   # Codex builds using this path
  "$env:USERPROFILE\.gemini\skills\video-quang-cao-v3",   # Gemini user scope
  "$env:USERPROFILE\.claude\skills\video-quang-cao-v3"   # Claude Code user scope
)
foreach ($target in $targets) {
  New-Item -ItemType Directory -Force -Path (Split-Path $target) | Out-Null
  Copy-Item -LiteralPath $source -Destination $target -Recurse -Force
}
```

Nếu chỉ dùng một agent, chỉ cần chép vào thư mục tương ứng. Cách dùng thư mục `.agents/skills` là lựa chọn dùng chung cho các agent hỗ trợ chuẩn Agent Skills; thư mục riêng giúp tương thích với agent có bộ quét riêng.

## Cài theo từng công cụ

### Codex desktop, CLI hoặc IDE

- Cấp repo: giữ nguyên `.agents/skills/video-quang-cao-v3/` và khởi chạy Codex bên trong repo.
- Cấp người dùng: chép vào `%USERPROFILE%\.agents\skills\video-quang-cao-v3\` (hoặc `%USERPROFILE%\.codex\skills\video-quang-cao-v3\` nếu bản Codex đang dùng quét thư mục cũ).
- Mở lại Codex nếu skill mới chưa xuất hiện; trong Codex CLI/IDE có thể gõ `/skills` để xem danh sách rồi dùng `$video-quang-cao-v3`.

### Gemini CLI

- Cấp repo: giữ skill trong `.agents/skills/video-quang-cao-v3/`.
- Cấp người dùng: sau khi clone, dùng `gemini skills install "$repo\.agents\skills\video-quang-cao-v3"` hoặc chép thư mục vào `%USERPROFILE%\.gemini\skills\video-quang-cao-v3\`.
- Kiểm tra `/skills list`; sau khi cập nhật dùng `/skills reload`. Nếu agent yêu cầu quyền kích hoạt skill, chấp thuận sau khi đã xem nội dung repo.

### Claude Code

- Cấp dự án: chép vào `.claude/skills/video-quang-cao-v3/` trong repo dự án cần dùng.
- Cấp cá nhân: chép vào `%USERPROFILE%\.claude\skills\video-quang-cao-v3\` để dùng cho mọi dự án.
- Gọi `/video-quang-cao-v3` hoặc hỏi trực tiếp về quảng cáo sản phẩm. Claude Code hỗ trợ tự nạp lại thay đổi trong thư mục skill; nếu vừa tạo thư mục cấp cao mới, khởi động lại phiên.

### Agent khác hỗ trợ Agent Skills

Tìm thư mục skills cá nhân của agent đó, rồi chép nguyên thư mục `video-quang-cao-v3` vào. Giữ nguyên tên file `SKILL.md`, các thư mục `references`, `assets` và `agents`. Agent phải đọc `SKILL.md` trước khi áp dụng; nếu có cơ chế reload/discovery, chạy cơ chế đó sau khi chép.

## Cập nhật phiên bản

```powershell
cd "$env:USERPROFILE\Documents\GitHub\kichban_hoathinh_2d_print"
git pull
```

Sau đó chạy lại đoạn cài đặt ở trên để đồng bộ bản mới vào thư mục người dùng. Không sửa trực tiếp bản đã chép trong thư mục agent nếu muốn lần sau cập nhật từ repo không bị mất thay đổi.

## Mẫu yêu cầu

```text
$video-quang-cao-v3
Tạo video 45 giây cho sản phẩm trong ảnh.
Công dụng/đặc điểm đúng mẫu: ...
Mỗi clip nguồn dài 6 giây, khung 16:9.
Công cụ đã đặt sẵn background, không mô tả background trong prompt.
```

Skill sẽ trả về prompt dán hàng loạt, lời đọc liền mạch và bảng nhịp dựng. Nếu không ghi thời lượng, agent cần hỏi 30/45/60/90 giây hoặc thời lượng tùy ý; không tự đoán số cảnh. Các claim về sức khỏe, tính năng kỹ thuật, giá và ưu đãi phải có căn cứ từ thông tin đúng mẫu.

## Tham khảo

- [OpenAI — Build skills](https://learn.chatgpt.com/docs/build-skills)
- [Gemini CLI — Managing Agent Skills](https://geminicli.com/docs/cli/using-agent-skills/)
- [Claude Code — Extend Claude with skills](https://code.claude.com/docs/en/slash-commands)
