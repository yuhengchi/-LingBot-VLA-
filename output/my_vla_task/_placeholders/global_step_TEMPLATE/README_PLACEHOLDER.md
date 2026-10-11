# DCP 后训练检查点占位

此目录仅展示预期结构，不能恢复训练或转换权重。
真实训练器会在 output/my_vla_task 下生成 global_step_<实际步数> 目录。
model 与 optimizer 内的 .metadata 和 .distcp 由 PyTorch DCP 自动生成；文件数量、分片名以及其他训练状态以真实输出为准。
此示例放在 _placeholders 子目录内，以免被当作可恢复的 global_step 检查点。
