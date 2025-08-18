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

**任务名称**: calculate population on barrio
**任务文件**: barrio_population_calculate.ipynb
**文件路径**: CASA0004arrio_population_calculate.ipynb
**数据集**: 2016 Barrio & 2018 cencus on MANZANA
**代码版本**: v1.0_G, (first part of geo cleaning)
**输入目录**: E:\Dissertation\CASA0004\Barrios_will_UPZ.geojson
**输出目录**: E:/Dissertation/XGBoost_cleaning/barrio_with_population
**状态**: 完成，存在少量很恐怖的异常值
**耗时**: 43.2
**备注**: 1.用barrio边界与manzana，按地理位置聚合，计算barrio的人口并且记录在"population"里面。2.如果街区完全包含了manzana，那就把全部的人口都算给它，如果没完全包含，就算[manzana总人口*(重叠面积/manzana的面积(这个数据记录在manzana的shape_area里面))]，四舍五入；3.完成后计算barrio的人口密度，为population/shape_area(这个是barrio数据集的shape_area)
**记录时间**: 2025-08-16 21:04:03

================分割线================

**任务名称**: calculate population on barrio
**任务文件**: barrio_population_calculate2.0.ipynb
**文件路径**: CASA0004arrio_population_calculate2.0.ipynb
**数据集**: 2016 Barrio & 2018 cencus on MANZANA
**代码版本**: v1.0_G, (first part of geo cleaning)
**输入目录**: E:\Dissertation\CASA0004\Barrios_will_UPZ.geojson
**输出目录**: E:/Dissertation/XGBoost_cleaning/barrio_with_population2
**状态**: 完成，存在192万异常值，后面在QGIS对空值和0值异常值进行了筛选
**耗时**: 50s
**备注**: 1.用barrio边界与manzana，按地理位置聚合，计算barrio的人口并且记录在"population"里面。2.如果街区完全包含了manzana，那就把全部的人口都算给它，如果没完全包含，就算[manzana总人口*(重叠面积/manzana的面积(这个数据记录在manzana的shape_area里面))]，四舍五入；3.完成后计算barrio的人口密度，为population/shape_area(这个是barrio数据集的shape_area)
**记录时间**: 2025-08-18 16:59:53

================分割线================

**任务名称**: 转为CSV
**任务文件**: barrio_population_calculate2.0.ipynb
**文件路径**: CASA0004arrio_population_calculate2.0.ipynb
**数据集**: 2016 JSON & 2016 barrio with pop density
**代码版本**: v1.2_G, (2 part of geo cleaning)
**输入目录**: E:\Dissertation\XGBoost_cleaning\2016central_Mask2Former_with_geobarriokilling_SelectedSegClass
**输出目录**: E:\Dissertation\XGBoost_cleaning\2016central_Mask2Former_with_geobarriokilling_SelectedSegClass_Transtocsv
**状态**: 完成，只输出了当前区块的brrio
**耗时**: 50s
**备注**: 1.把每张图片的fence,wall,Road,Sidewalk,Building,Person,Bicyclist,Motorcyclist,Other Rider,Sky,Vegetation,Street Light这些离散的segement转为比率与计数变量,比率变量：fence,wall,Road,Sidewalk,Building,Sky,Vegetation（在一张图片里面的占比，字段形如"area_ratio": 0.310933），计数变量: Person,Bicyclist,Motorcyclist,Other Rider,Street light提取它在一张图片，（一个json里面的出现次数）,json里面的经纬度，upz码等变量请保留，在这一步完成后输出一个csv,一行是一个json的信息2.以barrio名称为group的依据，计算各项在某barrio下的平均值,一个barrio为一行，上述的各个变量为列；按照barrio名匹配geojson（这个json里面有人口数和密度数据）用图片识别输出json里面我整合过的谋杀量去除barrio json里面的population算谋杀率出来，这个是因变量3.在以上分组匹配完成后输出一个能进XGBoost的csv
**记录时间**: 2025-08-18 17:58:04

================分割线================

任务名称: central_detect_G&G 任务文件: RF_DETR_medium_G&G 文件路径: colab_RF_DETR_medium_G&G 数据集: 2016 central SVI 代码版本: v1.0_R, (first part of re_detr) 输入目录: /content/drive/MyDrive/Dissertation2/2016south_image_final 输出目录: /content/drive/MyDrive/Dissertation2/2016south_image_final_GG 状态: 南部识别涂鸦垃圾完成 耗时: 2h 备注: 输出json，包含垃圾和涂鸦数量，每200张图片分一个batch保存 记录时间: 2025-08-18 18:15:19

================分割线================

