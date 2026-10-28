# Workspace Rules for Japan2027

## Automatic Google Drive / Google Docs Sync
Whenever you update `/home/lupos/Documents/Japan2027/mt_fuji_ryokan_guide.html` (or any travel guide in this workspace), automatically sync it in place to the user's Google Drive using `rclone`:

1. Update the raw `.html` backup file on Google Drive (`mt_fuji_ryokan_guide_raw.html`, kept under a distinct filename so it never collides with the Google Doc):
   ```bash
   ~/.local/bin/rclone copyto /home/lupos/Documents/Japan2027/mt_fuji_ryokan_guide.html "gdrive:mt_fuji_ryokan_guide_raw.html" --ignore-times
   ```
2. Update the live Google Doc (`https://docs.google.com/document/d/1teRQUz6sXaHKKL3JF4V59yYNGFoOq3bVGLVA3k0vPIs/edit`) in place:
   ```bash
   ~/.local/bin/rclone copyto /home/lupos/Documents/Japan2027/mt_fuji_ryokan_guide.html "gdrive:mt_fuji_ryokan_guide.html" --drive-import-formats html --drive-export-formats html --ignore-times
   ```
