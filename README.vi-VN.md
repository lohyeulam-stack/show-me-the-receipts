<p align="center"><img src="./logo.png" alt="Show Me The Receipts — kỹ năng đầu ra dựa trên bằng chứng" width="140" /></p>

<h1 align="center">Show Me The Receipts</h1>

<p align="center"><strong>Có bằng chứng không. Ngăn AI chôn câu trả lời dưới những lời hoa mỹ.</strong></p>

<p align="center">
  <a href="LICENSE"><img src="https://img.shields.io/badge/license-MIT-blue.svg" alt="MIT License"></a>
  <a href="https://github.com/lohyeulam-stack/show-me-the-receipts/releases"><img src="https://img.shields.io/badge/release-v0.1.0-informational" alt="Release"></a>
  <a href="#-install"><img src="https://img.shields.io/badge/Claude%20Code-plugin-blue?style=flat" alt="Claude Code plugin"></a>
  <img src="https://img.shields.io/badge/PRs-welcome-brightgreen.svg" alt="PRs welcome">
</p>

<p align="center">
  <a href="README.md" title="English" aria-label="English">🇬🇧 English</a> ·
  <a href="README.zh-CN.md" title="简体中文" aria-label="简体中文">🇨🇳 简体中文</a> ·
  <a href="README.zh-TW.md" title="繁體中文" aria-label="繁體中文">🇨🇳 繁體中文</a> ·
  <a href="README.ja-JP.md" title="日本語" aria-label="日本語">🇯🇵 日本語</a> ·
  <a href="README.ko-KR.md" title="한국어" aria-label="한국어">🇰🇷 한국어</a> ·
  <a href="README.es-ES.md" title="Español" aria-label="Español">🇪🇸 Español</a> ·
  <a href="README.pt-BR.md" title="Português (Brasil)" aria-label="Português (Brasil)">🇧🇷 Português (Brasil)</a> ·
  <a href="README.fr-FR.md" title="Français" aria-label="Français">🇫🇷 Français</a> ·
  <a href="README.de-DE.md" title="Deutsch" aria-label="Deutsch">🇩🇪 Deutsch</a> ·
  <a href="README.ru-RU.md" title="Русский" aria-label="Русский">🇷🇺 Русский</a> ·
  <strong title="Tiếng Việt" aria-label="Tiếng Việt">🇻🇳 Tiếng Việt</strong>
</p>

**Show Me The Receipts** là skill mã nguồn mở (MIT) cho agent AI, buộc báo cáo, retrospective, code review và bản tin trạng thái theo kỷ luật bằng chứng: kết luận ở dòng đầu, tách biệt sự thật / phán đoán / chưa biết, mọi hành động có người phụ trách · hạn chót · sản phẩm nghiệm thu được — loại bỏ giọng văn AI, định dạng thân thiện ADHD mặc định.

## Cài đặt

```bash
claude plugin marketplace add lohyeulam-stack/show-me-the-receipts
claude plugin install show-me-the-receipts@show-me-the-receipts
```

Khởi động lại rồi gõ `/show-me-the-receipts`. Codex / Cursor / OpenCode / LLM web: [INSTALL.md](INSTALL.md).

## Vì sao

Báo cáo chết vì những câu rỗng: *"tiến triển ổn định", "team dev đang theo", "xử lý sớm nhất"* — đọc xong không ai biết chuyện gì xảy ra, kẹt ở đâu, hỏi ai. LLM giỏi đúng kiểu thất bại này.

Skill này đứng trên vai hai dự án tuyệt vời mà chúng tôi biết ơn: [op7418/Humanizer-zh](https://github.com/op7418/Humanizer-zh) cung cấp danh sách dấu vết viết AI tiếng Trung cho luật chống slop; [ayghri/i-have-adhd](https://github.com/ayghri/i-have-adhd) cung cấp lớp định dạng ADHD và kiến trúc plugin. Trên nền đó, repo này thêm tầng mới: phân hạng bằng chứng, bộ ba hành động, kỷ luật tài liệu chính thức và retrospective.

## Before / After

**😵 Before**
> Câu hỏi hay! Quý này tiến triển ổn định. Phần tích hợp sẽ sớm được xử lý. Tương lai rực rỡ!

**🧾 After**
> Campaign Update lỗi ở bước kiểm tra `budget_mode`: error code 30100, 4 Campaign không lưu được (tính đến 17/09 16:00).
> - Target: 10 · Actual: 7 · Gap: −3, đạt 70%
> - Cause: 2 kẹt ở kiểm tra tham số TikTok API, 1 chờ quyền tài khoản thật
> - Bước tiếp — người phụ trách: Backend A · hạn: 18/09 18:00 · sản phẩm: log request thành công/thất bại kèm error code
> - "Còn dư địa cải thiện": không có dữ liệu → **chưa biết**

## 10 luật

1. Dòng đầu là kết luận hoặc hành động tiếp theo. Cấm mở đầu và "hy vọng hữu ích!".
2. Bốn hạng bằng chứng: sự thật đã kiểm chứng / kinh nghiệm truy vết được / suy đoán có nhãn / ý kiến.
3. Không biết thì ghi không biết. Cấm bịa số liệu, thời gian, người phụ trách, quan hệ nhân quả.
4. Bộ ba hành động: người phụ trách · hạn chót · sản phẩm.
5. Năm loại cụ thể hoá: chủ thể, thời gian, kết quả, vấn đề, phương án.
6. Tiến độ theo Target / Actual / Gap / Cause.
7. Kỷ luật tài liệu: không meta, đoạn dẫn sau mỗi đề mục, cấm từ vô nghĩa.
8. Chẩn đoán retro: phán đoán kèm bằng chứng, giữ nguyên văn trích dẫn, chuỗi nhân quả, phê bình đúng đích.
9. Chống slop AI: xoá mở đầu thừa, từ hoa mỹ, quy kết mơ hồ, khoảng giả.
10. Thân thiện ADHD: bước đánh số, nhắc lại trạng thái mỗi lượt, ước lượng thời gian cụ thể, danh sách ≤ 5.

Toàn văn: [SKILL.md](./skills/show-me-the-receipts/SKILL.md)

## Bật thường trực

```bash
touch ~/.claude/.show-me-the-receipts-always
```

## FAQ

**Quan hệ với i-have-adhd và Humanizer-zh?**
Trên hết là lòng biết ơn: lớp định dạng ADHD và cấu trúc repo đến từ i-have-adhd; từ vựng chống slop tiếng Trung đến từ Humanizer-zh. Hãy tặng sao cho cả hai.

**Dùng tiếng Anh được không?**
Phân hạng bằng chứng, bộ ba hành động, báo cáo Gap không phụ thuộc ngôn ngữ. Danh sách từ slop thiên về tiếng Trung; PR cho tiếng Anh được chào đón.

## Credits

- [op7418/Humanizer-zh](https://github.com/op7418/Humanizer-zh) — danh sách dấu vết viết AI tiếng Trung. Cảm ơn 🙏
- [ayghri/i-have-adhd](https://github.com/ayghri/i-have-adhd) — định dạng ADHD và đóng gói đa runtime. Cảm ơn 🙏

## License

[MIT](LICENSE)

---

<p align="center">Dùng xong nhớ dán bằng chứng. ⭐ nếu nó cứu bạn khỏi một câu "Câu hỏi hay!".</p>
