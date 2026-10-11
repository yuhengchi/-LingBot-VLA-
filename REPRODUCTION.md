# Local LingBot-VLA reproduction setup

This repository retains the upstream LingBot-VLA source and license, with local
configuration files for a grasp-and-place task. The added files describe setup
and artifact structure; they do not establish completed training or real-robot
results. No success-rate or timing claims are made here.

## Local additions

- `configs/robot_configs/myrobot.yaml`: tutorial robot feature mapping.
- `configs/vla/my_vla_task.yaml`: training settings and local artifact paths.
- `configs/vla/lingbotvla_cli.example.yaml`: reconstructed inference configuration;
  use the actual training-exported `lingbotvla_cli.yaml` with real checkpoints.
- `assets/norm_stats/myrobot.json`: normalization schema with empty arrays.
- `output/my_vla_task/`: configuration snapshot and explicitly marked DCP placeholders.
- `configs/vla/my_vla_task_placeholders.md`: artifact locations and format notes.

Paths beginning with `D:/vla` refer to the original Windows workspace and must be
adapted on another machine. The FSDP2 training configuration has not been
validated for native Windows training.

Model weights, datasets, virtual environments, calibration secrets and credentials
are not bundled. Files ending in `.placeholder` are empty format markers and
cannot be used as model weights, videos or checkpoints. Replace normalization
templates with statistics computed from the real training data.

The LeRobot source used during preparation is a separate checkout of
https://gitee.com/zhuzhuangtian/lerobot.git . See upstream documentation for
LeRobot v3.0 dataset requirements.

For the source project and model downloads, see the upstream README and
https://github.com/Robbyant/lingbot-vla .
