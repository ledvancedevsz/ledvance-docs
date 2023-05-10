# 萤石长链接API `1.0.1`

---

### 1. 家庭新增/删除

> 新增

- 需要触发长链接的API：`/v3/family/sync/batchAdd` `/v3/family/add`

- 长链接推送数据格式

```json
{
  "pushType": 3,
  "badge": 0,
  "id": "1654289784546631680",
  "alert": "",
  "ext": "{\"familyId\":11838,\"masterId\":\"75caa57b8ecd4db88e7f30486b7acc93\",\"senderId\":\"75caa57b8ecd4db88e7f30486b7acc93\",\"activeType\":\"add\",\"familyName\":\"Home\",\"x-type\":\"familyEvent\",\"eventType\":\"family\",\"userId\":\"75caa57b8ecd4db88e7f30486b7acc93\"}",
  "pushTime": 1683248394513
}
```

> 删除

- 需要触发长链接的API：`/v3/family/{familyId}/delete`

- 长链接推送数据格式

```json
{
  "pushType": 3,
  "badge": 0,
  "id": "1654292025970106368",
  "alert": "",
  "ext": "{\"familyId\":11838,\"masterId\":\"75caa57b8ecd4db88e7f30486b7acc93\",\"senderId\":\"75caa57b8ecd4db88e7f30486b7acc93\",\"activeType\":\"delete\",\"familyName\":\"Home\",\"x-type\":\"familyEvent\",\"eventType\":\"family\",\"userId\":\"75caa57b8ecd4db88e7f30486b7acc93\"}",
  "pushTime": 1683248928908
}
```

### 2. 房间新增/删除/扩展字段变更

> 新增

- 需要触发长链接的API：`/v3/family/sync/batchAdd` `/v3/devices/resources/group`

- 长链接推送数据格式

```json
{
  "pushType": 3,
  "badge": 0,
  "id": "1656105301115740160",
  "alert": "",
  "ext": "{\"familyId\":11384,\"x-type\":\"roomAdd\",\"roomId\":55524}",
  "pushTime": 1683681247397
}
```

> 删除

- 需要触发长链接的API：`/v3/devices/resources/group/{groupId}`

- 长链接推送数据格式

```json
{
  "pushType": 3,
  "badge": 0,
  "id": "1654290678772244480",
  "alert": "",
  "ext": "{\"familyId\":11838,\"x-type\":\"roomDel\",\"roomId\":54470}",
  "pushTime": 1683248607711
}
```

> 扩展字段变更

- 需要触发长链接的API：`/v3/devices/resources/group/{groupId}?ignoreMembers=true`

- 长链接推送数据格式

```json
{
  "pushType": 3,
  "badge": 0,
  "id": "1654290471417356288",
  "alert": "",
  "ext": "{\"familyId\":11838,\"x-type\":\"roomStateChanged\",\"roomId\":54470}",
  "pushTime": 1683248558274
}
```

### 3. 设备新增/删除

> 新增

- 需要触发长链接的API：`/v3/devices/sync/batchAdd` `/v3/devices/sync/add`

- 长链接推送数据格式

```json
{
  "pushType": 3,
  "badge": 0,
  "id": "1654291527078617088",
  "alert": "",
  "ext": "{\"deviceSerial\":\"LDV_MESH_TEMPERATURE_DEVICE:5B8F6615FA68EE31829F23538ABF97C9\",\"groupId\":54466,\"key\":\"addDevice\",\"userId\":\"75caa57b8ecd4db88e7f30486b7acc93\",\"version\":\"v3\",\"x-type\":\"userDevEvent\"}",
  "pushTime": 1683248809963
}
```

> 删除

- 需要触发长链接的API：`v3/devices/sync/{deviceId}`

- 长链接推送数据格式

```json
{
  "pushType": 3,
  "badge": 0,
  "id": "1654290924306800640",
  "alert": "",
  "ext": "{\"deviceSerial\":\"LDV_MESH_TEMPERATURE_DEVICE:5B8F6615FA68EE31829F23538ABF97C9\",\"groupId\":52550,\"key\":\"delDevice\",\"userId\":\"75caa57b8ecd4db88e7f30486b7acc93\",\"version\":\"v3\",\"x-type\":\"userDevEvent\"}",
  "pushTime": 1683248666251
}
```
