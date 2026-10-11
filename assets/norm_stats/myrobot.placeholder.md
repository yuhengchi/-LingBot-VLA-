# 归一化统计占位

myrobot.json 中 mean/std/q01/q99 均为空数组，count=0，不包含真实统计量。
当前 myrobot.yaml 切片得到 arm.position 12 维、effector.position 2 维。
mean/std 等统计应与切片后的特征维度一致；训练配置中的 arm.position: 14 是后续补齐上限。
不要填入全零均值、全一标准差来冒充实际统计。
准备好真实训练集后，使用 scripts/compute_norm.py 和 configs/vla/my_vla_task.yaml 生成并替换该文件。
