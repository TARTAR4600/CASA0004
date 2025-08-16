## 2025-08-15 16:01
**任务名称**: filter_barrios
**数据集**: Barrios
**代码版本**: v1.0
**输入目录**: /content/CASA0004
**输出目录**: /content/CASA0004
**状态**: 完成
**耗时**: null
**备注**: 匹配完成，但是Geojson里面存在重复街区，大约十几个，后续步骤需要注意去重

## 2025-08-15 16:02
**任务名称**: filter_barrios
**数据集**: Barrios
**代码版本**: v1.0
**输入目录**: /content/CASA0004
**输出目录**: /content/CASA0004
**状态**: 完成
**耗时**: null
**备注**: 匹配完成，但是Geojson里面存在重复街区，大约十几个，后续步骤需要注意去重

## 2025-08-15 16:04
**任务名称**: filter_barrios
**数据集**: Barrios
**代码版本**: v1.0
**输入目录**: /content/CASA0004
**输出目录**: /content/CASA0004
**状态**: 完成
**耗时**: null
**备注**: 匹配完成，但是Geojson里面存在重复街区，大约十几个，后续步骤需要注意去重

## 2025-08-15 16:04
**任务名称**: filter_barrios
**数据集**: Barrios
**代码版本**: v1.0
**输入目录**: /content/CASA0004
**输出目录**: /content/CASA0004
**状态**: 完成
**耗时**: null
**备注**: 匹配完成，但是Geojson里面存在重复街区，大约十几个，后续步骤需要注意去重

**任务名称**: match_point_barrio
**数据集**: Bogota_points
**代码版本**: v1.0
**输入目录**: E:/Dissertation/XGBoost_cleaning/2016central_Mask2Former_with_geo
**输出目录**: E:/Dissertation/XGBoost_cleaning/2016central_Mask2Former_with_geobarrio
**状态**: finished
**耗时**: 1220.3516931533813
**备注**: 每200个point生成一个batch，匹配Barrios社区+UPZ

**任务名称**: reclass 2016 homicide
**数据集**: original_homicide
**代码版本**: group_barrio_homicide_2016
**输入目录**: homicidios-en-bogota-2016.csv
**输出目录**: 2016homicide_barrio_upz_barriocount_final.csv
**状态**: 完成
**耗时**: none
**备注**: 第一次根据barrio名筛选聚合的数据，没做匹配

**任务名称**: join kill count
**数据集**: Bogota_points
**代码版本**: v1.1(based on json_interselect.ipynb)
**输入目录**: E:/Dissertation/XGBoost_cleaning/2016central_Mask2Former_with_geobarrio
**输出目录**: E:/Dissertation/XGBoost_cleaning/2016central_Mask2Former_with_geobarriokilling
**状态**: 完成
**耗时**: 1m57s
**备注**: 保持原有batch结构，增加了杀人数量字段(Cantidad)，用Matched_Barrio和json里面的barrio字段匹配，匹配前要把json里面的都变小写,无匹配的数量计0

================分割线================

**任务名称**: filter 
**数据集**: 2016central_Mask2Former_with_geobarriokilling
**代码版本**: v1.3(third part of cleaning)
**输入目录**: E:/Dissertation/XGBoost_cleaning/2016central_Mask2Former_with_geobarriokilling
**输出目录**: E:/Dissertation/XGBoost_cleaning/2016central_Mask2Former_with_geobarriokilling_SelectedSegClass
**状态**: finished
**耗时**: 1m57s
**备注**: 保持原有batch结构,只保留fence,wall,Road,Sidewalk,Building,Person,Bicyclist,Motorcyclist,Other Rider,Sky,Vegetation,Street Light相关字段
**记录时间**: 2025-08-16 19:28:56

================分割线================

