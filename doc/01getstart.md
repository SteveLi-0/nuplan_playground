# NuPlan 仿真评估教程

## 开环测试教程
开环测试是指自动驾驶车辆根据其预测的轨迹进行仿真，主要考虑因素为预测轨迹和自主轨迹的位移偏差、航向角偏差等。

### 开环仿真步骤：
1. 激活 `nuplan` 环境：
   ```bash
   conda activate nuplan
   ```

2. 进入 `nuplan-devkit` 目录：
   ```bash
   cd nuplan-devkit
   ```

3. 运行 `simple_planner` 的开环仿真程序：
   ```bash
   python nuplan/planning/script/run_simulation.py \
   +simulation=open_loop_boxes \
   planner=simple_planner \
   scenario_builder=nuplan_mini \
   scenario_filter=all_scenarios \
   scenario_filter.scenario_types="['near_multiple_vehicles, on_pickup_dropoff, starting_unprotected_cross_turn, high_magnitude_jerk']" \
   scenario_filter.num_scenarios_per_type=10
   ```

4. 运行 `nuboard` 程序，跳转到浏览器：
   ```bash
   python nuplan/planning/script/run_nuboard.py
   ```

---

## 无响应闭环测试教程
无响应测试指的是自动驾驶车辆是否对自主运动有反应分为：无响应闭环和有响应闭环。

### 无响应闭环仿真步骤：
1. 激活 `nuplan` 环境：
   ```bash
   conda activate nuplan
   ```

2. 进入 `nuplan-devkit` 目录：
   ```bash
   cd nuplan-devkit
   ```

3. 运行 `simple_planner` 的无响应闭环仿真程序：
   ```bash
   python nuplan/planning/script/run_simulation.py \
   +simulation=closed_loop_nonreactive_agents \
   planner=simple_planner \
   scenario_builder=nuplan_mini \
   scenario_filter=all_scenarios \
   scenario_filter.scenario_types="['near_multiple_vehicles, on_pickup_dropoff, starting_unprotected_cross_turn, high_magnitude_jerk']" \
   scenario_filter.num_scenarios_per_type=10
   ```

4. 运行 `nuboard` 程序，跳转到浏览器：
   ```bash
   python nuplan/planning/script/run_nuboard.py
   ```

5. 在浏览器中，点击 `Upload file`，选择路径为：
   ```
   ~/nuplan/exp/exp/simulation/closed_loop_nonreactive_agents/xxxx
   ```
   的文件，并在 Overview 界面中查看无响应闭环测试的结果。

以下是从图片中提取的内容，并将其以 Markdown 格式添加在之前的文档后面：


## 有响应闭环测试教程
有响应闭环是指社会车辆对自主车辆的行为有响应。在终端中输入如下指令，运行 `simple_planner` 的有响应闭环仿真程序：

1. 激活 `nuplan` 环境：
   ```bash
   conda activate nuplan
   ```

2. 进入 `nuplan-devkit` 目录：
   ```bash
   cd nuplan-devkit
   ```

3. 运行 `simple_planner` 的有响应闭环仿真程序：
   ```bash
   python nuplan/planning/script/run_simulation.py \
   +simulation=closed_loop_reactive_agents \
   planner=simple_planner \
   scenario_builder=nuplan_mini \
   scenario_filter=all_scenarios \
   scenario_filter.scenario_types="['near_multiple_vehicles, on_pickup_dropoff, starting_unprotected_cross_turn, high_magnitude_jerk']" \
   scenario_filter.num_scenarios_per_type=10
   ```

4. 运行 `nuboard` 程序，跳转到浏览器：
   ```bash
   python nuplan/planning/script/run_nuboard.py
   ```

5. 在浏览器中，点击 `Upload file`，选择路径为：
   ```
   ~/nuplan/exp/exp/simulation/closed_loop_reactive_agents/xxxx
   ```
   的文件，并在网页的 Overview 界面中查看有响应闭环测试的结果。
