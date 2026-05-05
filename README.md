# Gagauz hikâyeler

Gagauz dilinde destanlar, efsaneler hem masallar içün veb-sayt. Repozitoriu yalın statik HTML içerir; yayın **GitHub Pages** üzerinden **GitHub Actions** ile yapılır.

## GitHub Pages ayarı

1. Repoda **Settings → Pages** bölümüne gir.
2. **Build and deployment** altında **Source** olarak **GitHub Actions** seç.
3. `main` branchına push et; **Actions** sekmesinden «Deploy GitHub Pages» işinin bittiğini kontrol et.
4. Site URLi: `https://<istifadeçi-adı>.github.io/<repo-adı>/` (project Pages).

Sayfa kökü `public/` klasörüdür; buraya HTML, CSS hem görselleri koy.

## Yapay zekâ kömekçileri (Claude Code, Codex, Copilot, OpenCode, Cursor)

Repoda ortak talimatlar **`AGENTS.md`** dosyasında. **Claude Code** başlangıçta **`CLAUDE.md`** üzerinden bunu yüklüyor (`@AGENTS.md`). **GitHub Copilot** içün: **`.github/copilot-instructions.md`**. **Cursor** içün: **`.cursor/rules/*.mdc`**. Bi yeri deñiştiriksen, maslahat: eñ aza **AGENTS.md** hem **copilot-instructions** içindeki kısaca kurallar aynı kalsın.
