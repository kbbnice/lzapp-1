#### echart-map: 

1. 地图上城市名字位置修改：

```json
{
    "type":"Feature",
 "properties":{
     "name":"秀屿区",
     "id":"350305",
     
     //**修改这里可以改变城市名位置**
     //其中： 前面为经度， 后面为纬度。（具体位置可以去百度、谷歌等地图复制经纬度，再作调整）
     "cp":[119.1371960602,25.2718390269]},	
    //*************
    
     "geometry": {
        "type": "MultiPolygon",
         "coordinates": []		//somecode about position
     }
}

```

