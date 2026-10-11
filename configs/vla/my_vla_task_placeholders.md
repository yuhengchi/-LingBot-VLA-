# 尚缺产物与占位位置

| 产物 | 本地位置 | 目前状态 |
|---|---|---|
| LeRobot v3.0 训练数据 | D:/vla/datasets/biso102_pick_place | JSON 结构模板及二进制文件名占位，无真实数据 |
| LingBot-VLA 归一化统计 | D:/vla/lingbot-vla/assets/norm_stats/myrobot.json | 空统计数组，count=0 |
| 训练检查点 | D:/vla/lingbot-vla/output/my_vla_task/_placeholders/global_step_TEMPLATE | DCP 结构占位 |
| 后训练推理模型 | D:/vla/models/lingbot-vla-4b-posttrained | 文件名占位，无权重 |

所有 .placeholder 文件都是零字节文件，用于说明未来产物的文件名和格式，不能直接使用或靠重命名变成有效产物。
已有预训练模型和 Qwen 模型继续作为训练输入，配置未切换到空的后训练模型目录。
完成顺序：准备真实数据 → 按数据核对机器人映射 → 计算归一化统计 → 后训练生成 DCP → 导出推理模型。
归一化 JSON 中的 _placeholder/_note 为模板注释字段，生成真实统计后应被完整替换。
目前只创建本地占位文件，没有执行训练、数据转换或模型导出。
