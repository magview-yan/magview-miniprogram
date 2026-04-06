# MAGVIEW – Industrial Parts Visual Indexing System

MAGVIEW industrial machinery parts data acquisition mini-program.  
Project for standardized mechanical parts database building.

---

# 🌍 核心定位 (The Vision)

MAGVIEW 不仅仅是一个配件买卖系统，它是全球重卡（中国制造）售后市场的“数字身份证系统”。

我们将碎片化的海外维修配件，通过标准化的数据映射，转化为可检索、可识别的工业资产。

---

# 🧱 三层逻辑架构 (System Architecture)

## 第一层：全球化数据采集系统 (The Capture System)

- 前端工具：
  - 标准化物理拍照台（俯拍支架 + 环形灯 + MAGVIEW拍照垫）
- 采集逻辑：
  - VIN → 车型 → 配件分类 → OE号录入
  - 多视角标准照片上传
- 数据标准：
  - GPS坐标记录
  - 比例尺校验

---

## 第二层：UID统一编码中台 (The Core Database)

- 核心价值：
  - 建立 MAG-UID 体系
  - 打破不同主机厂 OE 号壁垒
- 数据映射：
  - OE号 → UID
  - 记录：
    - 尺寸
    - 材质
    - 参数
    - 故障频率

---

## 第三层：AI识别与检索引擎 (The Intelligent Engine)

- 匹配逻辑：
  - 预处理（透视校正 + 抠图）
  - 特征提取（形状 + OCR + 尺寸）
- 人工辅助机制：
  - AI提供候选
  - 人工确认
  - 持续优化

---

# 📊 系统流程图 (System Flow)

```mermaid
graph TD
    A[现场：旧零件采集] --> B(物理采集层)
    B --> C{特征提取层}
    
    subgraph AI_Engine [AI视觉核心引擎]
        C --> D[零件识别]
        C --> E[编码提取]
        D & E --> F[特征向量]
    end
    
    F --> G[(数据库)]
    G --> H{业务层}
    
    H --> I[OEM匹配]
    H --> J[采购推荐]
    H --> K[参数匹配]
