# ling-train

围绕《火车进站》（电影史）主题的**短视频自动化制作流水线**（ling-cinema）：完成素材采集、脚本、配音、字幕、帧图到成片的整条生产链路。

## 语言 / 类型

- 语言：Python 3（编排脚本）+ 媒体资产（mp4 / mp3 / wav / png / srt）
- 类型：离线视频制作流水线（依赖 ffmpeg 等外部工具与媒体资产）

## 目录要点

- `ling-cinema/`：主流水线脚本与成片（`audio_gen.py`、`build_video.py`、`generate_cards.py`、`final_compose.py` 等），含 `audio/`、`frames/`、`seg_png/`、`seg_vid/` 等中间产物
- `render/`：渲染辅助脚本（`gen_cards.py`、`make_timeline.py`、`prep.py`）
- `phase1_collection_report.md`、`phase2_production_pack.json`：阶段报告与生产包
- `火车进站_10分钟.mp4`：最终成片

## 运行方式与依赖

各脚本需外部依赖：

- `ffmpeg`（视频/音频合成）
- 相关媒体资产（原始视频、配音、帧图等，项目内已附带）
- 音频生成可能需要 TTS 工具

示例：

```bash
python ling-cinema/build_video.py
python ling-cinema/generate_cards.py
python render/gen_cards.py
```

## 测试状态

- 语法检查：通过（11 个 `.py` 文件无语法错误）
- 运行：需 ffmpeg 与媒体资产，未实际运行
