# Data sources and limitations

数据是网站功能的一部分，但不代表设施的实时状态。使用前请通过管理机构页面核实开放时间、关闭通知和现场可用性。

## DC parks

- 来源：[DC Open Data — Parks and Recreation Areas](https://opendata.dc.gov/datasets/DCGIS::parks-and-recreation-areas)
- 网站文件：`dist/data/parks.geojson`
- 用途：DC DPR 公园边界、名称、地址、区域和部分设施统计。
- 饮用水：依据数据中的 `DRINKFOUNT` / “Drinking Fountain” 字段。
- 限制：记录数量不保证设施当前正常工作；数据没有可靠的公共手机充电字段。

## National Park Service

- 来源：[NPS Data API](https://www.nps.gov/subjects/developer/api-documentation.htm)
- 网站文件：`dist/data/nps.json`
- 用途：位于华盛顿特区的 NPS 单位名称、类型、简介、官方网页和代表点位。
- 限制：代表点位不是完整公园边界，基础记录没有覆盖所有饮水、卫生间或充电位置。

## Rock Creek Park facilities

- 来源：[Rock Creek Park FAQ](https://www.nps.gov/rocr/faqs.htm)、[Operating Hours](https://www.nps.gov/rocr/planyourvisit/hours.htm)、[Nature Center & Planetarium](https://www.nps.gov/rocr/planyourvisit/nature-center-and-planetarium.htm)、[Peirce Mill](https://www.nps.gov/rocr/planyourvisit/peirce-mill-visitor-center.htm)
- 网站文件：`dist/data/nps-facilities.json`
- 用途：开放时间说明、游客中心、饮用水和卫生间设施。
- 限制：设施开放状态可能因季节、维护和人员安排变化。网站没有确认公共手机充电位置。

## Base map

- 地图图块：[OpenStreetMap](https://www.openstreetmap.org/)
- 地图运行库：[Leaflet](https://leafletjs.com/)
- 网站保留可见的 OpenStreetMap contributors 署名。

## Snapshot date

网站界面标记的数据快照范围为 2025–2026。提交更新时，应同时核实本文件、数据文件中的 `updated`/`retrieved` 字段和页面底部的数据日期。
