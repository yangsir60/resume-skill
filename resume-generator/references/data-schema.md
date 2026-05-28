# 简历 JSON 数据 Schema

## 必填字段

| 字段 | 类型 | 说明 |
|------|------|------|
| `name` | string | 中文姓名 |
| `nameEn` | string | 英文名（可选） |
| `contact.phone` | string | 电话 |
| `contact.email` | string | 邮箱 |
| `contact.birthday` | string | 生日 |
| `contact.location` | string | 居住地 |
| `education` | array | 教育经历，结构见下 |
| `experience` | array | 工作经历，结构见下 |
| `skills` | array | 个人技能 |

## 选填字段

| 字段 | 类型 | 说明 |
|------|------|------|
| `photo` | string | 照片路径（本地或URL），留空则显示占位框 |
| `hobbies` | array of string | 爱好列表（左侧栏展示） |
| `interests` | array of string | 兴趣标签（左侧栏圆形标签，推荐3个） |
| `projects` | array | 项目经历 |
| `awards` | array | 荣誉与证书 |
| `summary` | string | 自我介绍/一句话简介 |

---

## 教育经历结构 (education[])

```json
{
  "period": "2016 – 2020",
  "school": "三峡大学",
  "schoolEn": "Three Gorges University · Bachelor",
  "major": "计算机科学与技术",
  "detail": "平均学分绩点：2.72、加权平均成绩：81.66..."
}
```

## 工作经历结构 (experience[])

```json
{
  "period": "2022 – 至今",
  "company": "湖北中南鹏力海洋探测系统工程有限公司",
  "title": "算法工程师",
  "titleEn": "Algorithm Engineer",
  "detail": "主要从事高频地波雷达算法开发工作..."
}
```

## 项目经历结构 (projects[])

```json
{
  "title": "高频地波雷达远端显示平台维护与升级",
  "desc": "使用Qt对高频地波雷达远端显示平台进行维护与升级..."
}
```

## 荣誉证书结构 (awards[])

```json
{
  "items": ["初中数学教师资格证", "大学英语四级"]
}
```

## 个人技能结构 (skills[])

```json
["熟练掌握 Matlab 代码仿真、以及 C++ Qt 软件开发..."]
```

---

## 完整示例

```json
{
  "name": "杨树",
  "nameEn": "Yang Shu",
  "photo": "",
  "contact": {
    "birthday": "1998.09.02",
    "location": "湖北宜昌",
    "phone": "15872097002",
    "email": "1728421900@qq.com"
  },
  "hobbies": [
    "喜爱动手实践、较有耐心。",
    "喜欢研究一些电脑硬件。",
    "DIY过开源AWTRIX2.0像素时钟项目，可以显示时间也可以自定义显示其他内容。",
    "用YoloV5实现CSGO自动瞄准。"
  ],
  "interests": ["阅读", "音乐", "运动"],
  "education": [
    {
      "period": "2016 – 2020",
      "school": "三峡大学",
      "schoolEn": "Three Gorges University · Bachelor",
      "major": "计算机科学与技术",
      "detail": "平均学分绩点：2.72、加权平均成绩：81.66。2017年夏季在郑州蓝鸥实习学习，2019年夏季在中软国际进行了30天实训学习。"
    },
    {
      "period": "2020 – 2022",
      "school": "夷陵区马家湾小学",
      "schoolEn": "Work Experience",
      "major": "小学数学与信息技术教学",
      "detail": "于2021年参与了湖北省信息化教学创新培训（国培计划）。开发了多人在线打字程序，组织学生参与打字比赛，负责学校多媒体白板与计算机机房的运维管理。"
    }
  ],
  "experience": [
    {
      "period": "2022 – 至今",
      "company": "湖北中南鹏力海洋探测系统工程有限公司",
      "title": "算法工程师",
      "titleEn": "Algorithm Engineer",
      "detail": "主要从事高频地波雷达算法开发工作，现发表了一篇关于海洋雷达信号处理的专利处于实质审查阶段，参与撰写一篇发表在《Remote Sensing》期刊上的论文。"
    }
  ],
  "projects": [
    {
      "title": "高频地波雷达远端显示平台维护与升级",
      "desc": "使用Qt对高频地波雷达远端显示平台进行维护与升级，优化软件性能，实现地图上海洋径向流速的直观矢量箭头展示等。"
    },
    {
      "title": "地波雷达无源幅相校准算法开发",
      "desc": "利用MUSIC等算法对信号进行校准、提高信号准确度。"
    },
    {
      "title": "雷达风场反演算法",
      "desc": "开发雷达风场反演算法，提高风场反演精度。"
    },
    {
      "title": "雷达电离层识别与抑制",
      "desc": "开发雷达电离层识别与抑制算法，提高反应准确性。"
    },
    {
      "title": "船迹轨道预测程序",
      "desc": "结合遗传算法开发船迹轨道预测程序，为船舶航行提供优化路径建议。"
    }
  ],
  "awards": [
    { "items": ["初中数学教师资格证", "大学英语四级"] },
    { "items": ["2021年骨干信息教师培训结业证书", "2021年夷陵区信息技能比赛一等奖"] },
    { "items": ["专利《一种高频地波雷达径向流方位估计和流速合成方法及系统》（实质审查）"] }
  ],
  "skills": [
    "熟练掌握 Matlab 代码仿真、以及 C++ Qt 软件开发、会使用自适应梯度下降等优化算法。",
    "熟悉计算机机房运维管理。",
    "熟练 Python 数据处理与分析，及 LSTM 时间序列神经网络框架使用。"
  ]
}
```