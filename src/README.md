## Robot Package Template

This is a GitHub template. You can make your own copy by clicking the green "Use this template" button.

It is recommended that you keep the repo/package name the same, but if you do change it, ensure you do a "Find all" using your IDE (or the built-in GitHub IDE by hitting the `.` key) and rename all instances of `los_buenos_bot` to whatever your project's name is.

Note that each directory currently has at least one file in it to ensure that git tracks the files (and, consequently, that a fresh clone has direcctories present for CMake to find). These example files can be removed if required (and the directories can be removed if `CMakeLists.txt` is adjusted accordingly).

## Commands

Subir o robot_state_publisher junto com a simulação dentro do gazebo.

```bash
ros2 launch los_buenos_bot launch_sim.launch.py 
```

Subir o rviz com o arquivo de configuração correto

```bash
rviz2 -d ~/Documents/GitHub/my_bot/src/config/drive_bot.rviz
```

Launch do slam_toolbox para realizar o mapeamento do ambiente

```bash
ros2 launch los_buenos_bot online_async_launch.py params_file:=./src/config/mapper_params_online_async.yaml use_sim_time:=true
```

launch teleop

```bash
ros2 run teleop_twist_keyboard teleop_twist_keyboard
```


launch localization ro2s

```bash
ros2 launch los_buenos_bot localization_launch.py map:=./my_map_save.yaml  use_sim_time:=true
```

launch navigation launch

```bash
ros2 launch los_buenos_bot navigation_launch.py use_sim_time:=true map_subscribe_transient_local:=true
```

launch amcl

```bash
ros2 run nav2_util lifecycle_bringup amcl
```

TODO- fix na caster wheel fazendo o robo travar quando ele iniciar o movimento

TODO - fix na camera bugada dentro do rviz com a imagem

TODO - Fix no costmap criado.



