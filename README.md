# GIS 数据分析与制图

专题图、空间分析、遥感指数、批处理脚本，用 QGIS + Python 实现。每个仓库含可运行代码、数据说明与图件成品；图件按 GB/T 7713.2—2022 与 CY/T 171—2019 的图注规范排版，数据口径在 README 中逐项写明。

## 作品

| 仓库 | 内容 | 关键结果 | 技术栈 |
|---|---|---|---|
| [life-circle-accessibility](https://github.com/oliveriolikescoding/life-circle-accessibility) | 成都 1334 个住宅单元的 15 分钟生活圈可达性，医疗、教育、购物、公园、地铁 5 类设施，按 1000 m 内可达类别数分级 | 完备度 5 类 32.2%、4 类 29.4%、3 类 18.8%、2 类 11.7%、0—1 类 7.9% | Python + GeoPandas + PyQGIS |
| [ndvi-chengdu](https://github.com/oliveriolikescoding/ndvi-chengdu) | Sentinel-2 L2A 双期 NDVI，10 m 网格，SCL 云掩膜，跨期偏移校正 | 2025-01-03 均值 0.354，2026-01-12 均值 0.481；扣除偏移后改善 37.0%、退化 36.0%、稳定 27.0% | rasterio + GDAL + matplotlib + PyQGIS |
| [batch-ndvi](https://github.com/oliveriolikescoding/batch-ndvi) | 文件夹级批量 NDVI 计算，manifest 幂等、失败隔离、断点续跑、汇总出图 | 单景 0.1—0.2 s；4 景样例均值 0.433、0.393、0.156、0.047 | rasterio + argparse + pytest |
| [sichuan-population-map](https://github.com/oliveriolikescoding/sichuan-population-map) | 四川省 21 个市州常住人口分级设色图，七普 2020 | 成都 2094 万人，南充 561 万人，甘孜 110 万人 | QGIS + Python |
| [gis-interactive-map](https://github.com/oliveriolikescoding/gis-interactive-map) | 成都 15 分钟生活圈交互地图，1334 个住宅单元 × 846 个设施，单文件 HTML | 约 4 MB，离线可开，图层可切换 | Folium + GeoPandas |
| [coord_transform](https://github.com/oliveriolikescoding/coord_transform) | WGS84 与 GCJ-02 互转，点位表转 GeoJSON 并可出图 | 坐标先做范围校验，越界与非数值记录不入库 | Python + GeoPandas |
| [dem-30m-pack](https://github.com/oliveriolikescoding/dem-30m-pack) | 按经纬度范围从 Copernicus DEM GLO-30 裁 30 m 高程 | 样例 103.60—104.10°E / 30.90—31.40°N，高程 502—4495 m | rasterio + GDAL |
| [geo-etl-pipeline](https://github.com/oliveriolikescoding/geo-etl-pipeline) | OSM 生活设施端到端 ETL，6 步清洗每步记进出与理由，入 SQLite + GeoPackage 双库 | 4789 个原始要素 → 846 个设施、1334 个住宅单元、20 个区县、308 个地铁站；清洗后与既有成果逐条对账一致 | GeoPandas + SQLite + GeoPackage + matplotlib |
| [spatial-price-model](https://github.com/oliveriolikescoding/spatial-price-model) | 成都住宅单价的空间解释力与空间交叉验证 | 随机 5 折 R² 0.349，按区县分组 0.162，按片区分组 0.267；Moran's I 0.234（p 0.001） | scikit-learn + GeoPandas + scipy |
| [landuse-cnn](https://github.com/oliveriolikescoding/landuse-cnn) | EuroSAT RGB 八类地块影像分类与混淆诊断 | 手工特征基线 macro-F1 0.891，4-block CNN 0.866，ImageNet 预训练 ResNet18 0.955 | PyTorch + scikit-learn + scikit-image |
| [map-layout-qc](https://github.com/oliveriolikescoding/map-layout-qc) | 合成图件要素检测数据集，图题、图例、比例尺、指北针、色标、图注六类框由渲染器直接给出 | train 600 / val 100 / test 100，3988 个框，越界与零面积框 0 | matplotlib + Python + COCO |

## 图件与数据的口径

- 图件标注投影、平面基准、数据来源、许可、比例尺与图廓坐标；区县界线标注为非法定界线。
- 结论按实际样本与检验结果陈述：两个时相不构成趋势判断，10 m 像元分辨不出行道树。
- 代码许可 MIT，图件许可 CC BY 4.0。



