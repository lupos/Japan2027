# Workspace Rules for Japan2027

## Automatic GitHub Pages & Google Drive Sync
1. **Primary Live Website (`https://lupos.github.io/Japan2027/`):**
   Whenever you update `/home/lupos/Documents/Japan2027/index.html` (or any assets in `/home/lupos/Documents/Japan2027/`), commit and push to `origin main` so the live GitHub Pages site updates automatically:
   ```bash
   git add -A && git commit -m "Update Japan 2027 guide" && git push origin main
   ```

2. **Google Drive / Google Docs Sync (when updating `mt_fuji_ryokan_guide.html`):**
   ```bash
   ~/.local/bin/rclone copyto /home/lupos/Documents/Japan2027/mt_fuji_ryokan_guide.html "gdrive:mt_fuji_ryokan_guide_raw.html" --ignore-times
   ~/.local/bin/rclone copyto /home/lupos/Documents/Japan2027/mt_fuji_ryokan_guide.html "gdrive:mt_fuji_ryokan_guide.html" --drive-import-formats html --drive-export-formats html --ignore-times
   ```
