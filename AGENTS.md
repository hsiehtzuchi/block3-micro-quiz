# 跑台機分享版（Block 3）：GitHub 公開發布

本資料夾是公開儲存庫 https://github.com/hsiehtzuchi/block3-micro-quiz 的本機副本（2026-10-09 建，照 Block 1 的 `../micro_quiz_github/` 做）。只分享跑台機，筆記不放 GitHub。

- 儲存庫只放 `README.md`（給同學看的使用說明）、本檔、`.gitignore`。
- 測驗檔放在 **Release** 附件：`Block3_Micro_Quiz.html`（約 42 MB）與 `Block3_Micro_Quiz.zip`（約 30 MB）。附件檔名用英數字。
- 來源是 `~/Downloads/Block3_Micro_跑台測驗_分享版.html`（`../micro_quiz_block_20261008/build_block.py --block 3` 產生，key `b3micro_quiz_share_v1`，不讀使用者自己的紀錄）。不要放整合版。
- `dist/` 是上傳前的暫存，不進 git。
- 不能用 GitHub Pages：EBM 線上玻片是 http，https 頁面會擋。

## 更新（重建分享版之後）

```bash
cd ~/"Desktop/大四上/00_學習系統/tmp/micro_quiz_github_b3"
cp ~/Downloads/Block3_Micro_跑台測驗_分享版.html dist/Block3_Micro_Quiz.html
(cd dist && rm -f Block3_Micro_Quiz.zip && zip -q -9 Block3_Micro_Quiz.zip Block3_Micro_Quiz.html)
gh release create v$(date +%Y%m%d-%H%M) dist/Block3_Micro_Quiz.zip dist/Block3_Micro_Quiz.html --title "$(date +%Y-%m-%d) 版" --notes "<改了什麼、題數>"
```

- 發新版用新的 tag，README 的連結指向 `releases/latest`。
- 給班群的直接下載連結：https://github.com/hsiehtzuchi/block3-micro-quiz/releases/latest/download/Block3_Micro_Quiz.zip
- 發布前確認：分享版已跑過 `safari_check_block`（見 `../micro_quiz_block_20261008/AGENTS.md`）；README 題數正確；key 是 `b3micro_quiz_share_v1`。
