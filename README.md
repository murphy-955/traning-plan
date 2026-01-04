# 我的训练计划

## 初始化

```powershell
npm i docsify-cli -g

docsify serve docs
```

## GitHub pages 服务

[戳我](https://murphy-955.github.io/traning-plan/#/)

## Intellij IDEA 实时模板配置

1. 打开 Settings → Editor → File and Code Templates
2. 点击右上角的 + 号，选择 Live Template
3. 输入模板名称，如 `docsify`
4. 输入模板内容，作用域选择`Other`

### 1. plan-card

**模板内容：**

```
<div class="plan-container">
  <div class="plan-header">
    <div class="plan-date">$date$</div>
    <div class="$planType$">$planTypeDis$</div>
  </div>
  
  <hr class="divider">
  
  <div class="plan-time"> 
    <div class="plan-date">训练时间:</div>
    <span style="padding-top: 5px;">$time$</span>
  </div>
  
  <hr class="divider">
  
  <div class="plan-content">
    <h4>训练内容：</h4>
    
    <table class="workout-table">
      <thead>
        <tr>
          <th>距离</th>
          <th>泳姿</th>
          <th>内容</th>
          <th>说明</th>
        </tr>
      </thead>
      <tbody>
        $content$
      </tbody>
    </table>
  </div>
</div>
```

| 变量名           | 表达式                                                                                                                                                                              | 默认值 | 说明                                      |
|---------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----|-----------------------------------------|
| `date`        | `enum("周一", "周二", "周三", "周四", "周五", "周六", "周日")`                                                                                                                                 | /   | 周一到周日选一个                                |
| `planType`    | `enum("plan-purpose aerobic", "plan-purpose high-aerobic", "plan-purpose strength", "plan-purpose speed", "plan-purpose race-speed", "plan-purpose adjust","plan-purpose land")` | /   | 样式选择，根据训练目的选择，详见[style](docs/style.css) |
| `planTypeDis` | `enum("有氧", "高有氧", "力量", "速度", "比赛速度", "调整", "陆上")`                                                                                                                              | /   | 7种训练目的                                  |   
| `time`        | `"2026-01-01 10:00 - 2026-01-01 11:30"`                                                                                                                                          | /   | 训练时间                                    |
| `content`     | /                                                                                                                                                                                | /   | [蝶泳](#2-plan-list-detail)               |

### 2. plan-list-detail

**模板内容：**

```
<tr>
  <td><span class="workout-distance">$group$*$distance$</span></td>
  <td><span class="$swimmingTypeStyle$">$swimmingType$</span></td>
  <td><span class="workout-detail">$detial$</span></td>
  <td><span class="workout-note">$note$</span></td>
</tr>
```

| 变量名                 | 表达式                                                                                                                                                                       | 默认值 | 说明     |
|---------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----|--------|
| `group`             | `"1"`                                                                                                                                                                     | /   | 组数     |
| `distance`          | `"200"`                                                                                                                                                                   | /   | 距离     |
| `swimmingType`      | `enum("蝶泳", "仰泳", "蛙泳", "自由泳", "主项", "其他")`                                                                                                                               | /   | 泳姿     |
| `swimmingTypeStyle` | `enum("workout-stroke butterfly", "workout-stroke backstroke", "workout-stroke breaststroke", "workout-stroke freestyle", "workout-stroke main", "workout-stroke other")` | /   | 泳姿样式   |
| `detial`            | /                                                                                                                                                                         | /   | 具体该怎么游 |
| `note`              | /                                                                                                                                                                         | /   | 注意事项   |


