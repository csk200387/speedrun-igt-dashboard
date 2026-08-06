# Speedrun IGT Dashboard

A single-file HTML dashboard for browsing your Minecraft SpeedRunIGT completion records.<br>
Minecraft SpeedRunIGT 완주 기록을 확인할 수 있는 단일 HTML 대시보드입니다.

## Features

- Reads your SpeedRunIGT `records` folder directly in the browser — no server, no upload.<br>
  브라우저에서 SpeedRunIGT `records` 폴더를 직접 읽습니다 — 서버나 업로드가 필요 없습니다.
- Shows completed runs and failed/unfinished (DNF) attempts side by side.<br>
  완주한 런과 실패·미완주(DNF) 시도를 함께 보여줍니다.
- Approximates where a failed run ended — Overworld / Nether / Find Stronghold / End — from its timeline splits, since SpeedRunIGT itself doesn't record death coordinates or cause.<br>
  SpeedRunIGT는 사망 좌표나 원인을 기록하지 않으므로, 타임라인 스플릿을 근거로 실패한 런이 어느 구간(오버월드/네더/스트롱홀드 탐색/엔드)에서 끝났는지 근사해서 보여줍니다.
- Clear rate, total attempts, average IGT, total playtime, and latest PB at a glance.<br>
  클리어율, 총 시도 횟수, 평균 IGT, 총 플레이타임, 최근 PB를 한눈에 볼 수 있습니다.
- Per-run split table with segment times and delta vs. your PB.<br>
  런별 스플릿 테이블에서 구간 시간과 PB 대비 차이를 확인할 수 있습니다.
- Sort by newest/fastest, and filter by status (all/completed/failed) or world type (ranked/other).<br>
  최신순·빠른순 정렬과 상태(전체/완주/실패), 월드 종류(랭크드/기타) 필터를 지원합니다.

## Files

- `speedrun_records.html` — English version.<br>
  영문 버전입니다.
- `speedrun_records_ko.html` — Korean version.<br>
  한국어 버전입니다.

## Usage

1. Open either HTML file in a browser.<br>
   브라우저에서 두 HTML 파일 중 하나를 엽니다.
2. Click **Refresh** and select SpeedRunIGT's global `records` folder (path below).<br>
   **Refresh**(새로고침) 버튼을 누르고 아래 경로에 있는 SpeedRunIGT의 전역 `records` 폴더를 선택합니다.
3. Records are cached locally (IndexedDB), so the folder only needs to be picked once — next time the page loads instantly without prompting.<br>
   기록은 로컬(IndexedDB)에 캐시되어 폴더는 한 번만 선택하면 됩니다 — 다음부터는 다시 묻지 않고 바로 불러옵니다.

### Where the records folder is / 기록 폴더 위치

SpeedRunIGT collects records from every world into one global folder, not a per-world folder.<br>
SpeedRunIGT는 월드별이 아니라 하나의 전역 폴더에 모든 월드의 기록을 모읍니다.

| OS | Path |
|---|---|
| Windows | `%APPDATA%\speedrunigt\records` |
| macOS | `~/Library/Application Support/speedrunigt/records` |
| Linux | `~/.local/share/speedrunigt/records` (or `$XDG_DATA_HOME/speedrunigt/records` if set) |

## Note

Death location/cause isn't available in SpeedRunIGT's record files — the `ended in <phase>` label is an approximation based on the last split reached, not an exact death log.<br>
SpeedRunIGT 기록 파일에는 사망 위치·원인 정보가 없습니다 — `ended in <phase>` 표시는 정확한 사망 기록이 아니라 마지막으로 도달한 스플릿을 기준으로 한 근사치입니다.
