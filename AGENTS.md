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
- 傳上去的版本不能有 AI 老師對話視窗（2026-11-12 帥哥：「記得傳上去的版本不要有AI老師對話視窗（記住）」）：發布後把 Release 的 zip 下載解開，查沒有老師面板元素、問老師按鈕、127.0.0.1:8791 連線，CSS 註解提到不算。有就撤下、改分享版建置再發。

## 改動紀錄

- 2026-10-11 10:42：空間清理，`dist/`（Block3_Micro_Quiz.html、.zip，已發布在 GitHub Release v20261009-2349）搬到垃圾桶；下次發布照本檔步驟從 Downloads 的分享版重新產生。 使用者（經督導 session 轉達）：「全部可刪的都刪，除了 block 1 臨醫檢醫還沒考，先刪病理藥理的」 清單與逐筆紀錄：`~/Desktop/blender/work/cleanup_20261011/study_micro.md`、`MOVED_study_micro.log`；檔案在 `~/.Trash/cleanup_20261011/study_micro/`（保留家目錄下的相對路徑，清空垃圾桶前都能搬回）。
- 2026-11-12 13:30：發 v20261112-1321（11/10 21:21 分享版，31 片、心血管 B12 vol.9），Safari 分享版全部通過；README 改 31 片、純考古 EBM 14 題、心血管 B12；班群訊息草稿在 ../micro_quiz_share_20261112/班群訊息.md（帥哥：「幫我把現在github的跑台機整理成可以匯出的版本和訊息給同學」，選換成 11/10 新版）。
- 2026-11-13 08:16：發 v20261113-0816（11/12 14:53 分享版，md5 80d4bde8…，36 片：29–34 第二次範圍外、35–36 課表外兩個新分類；挑戰 117（M17、M23 空號）；純考古 B07–B11，EBM 25、挑戰版 18、不同器官 5）。發布前契約檢查 contract_b3_20261112.py PASS（分享版無 X-Teacher-Key）；14:53 寫進 Downloads 後 Safari 已全部通過，這次沒重跑。README 改 36 片、三類說明、zip 約 36 MB。帥哥：「幫我把跑台機更新上去github，一樣不要放老師功能，一樣記得讓上面的版本有分開的那八片播片分開放（最新版）」
- 2026-11-13 11:5x：發 v20261113-1151（11/13 11:48 分享版，md5 c68dfec0…）：範圍選單「全部」改 28 片（只出 01–28，29–36 只在自己的分類）。帥哥：「我要你全部36片那項變成只有28片的（範圍外移除）做完直接push」「整合版也要」。發布前 selfcheck 全符合、契約 PASS、Safari 整合版與分享版各 34 項全部通過；README 補一句「全部 28 片」。
