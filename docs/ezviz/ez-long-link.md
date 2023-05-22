# 萤石长链接API `1.1.0`

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
  "ext": {
    "familyId": 11838,
    "masterId": "75caa57b8ecd4db88e7f30486b7acc93",
    "senderId": "75caa57b8ecd4db88e7f30486b7acc93",
    "activeType": "add",
    "familyName": "Home",
    "x-type": "familyEvent",
    "eventType": "family",
    "userId": "75caa57b8ecd4db88e7f30486b7acc93"
  },
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
  "id": "1654289784546631680",
  "alert": "",
  "ext": {
    "familyId": 11838,
    "masterId": "75caa57b8ecd4db88e7f30486b7acc93",
    "senderId": "75caa57b8ecd4db88e7f30486b7acc93",
    "activeType": "delete",
    "familyName": "Home",
    "x-type": "familyEvent",
    "eventType": "family",
    "userId": "75caa57b8ecd4db88e7f30486b7acc93"
  },
  "pushTime": 1683248394513
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
  "id": "1654289784546631680",
  "alert": "",
  "ext": {
    "familyId": 11838,
    "roomId": 3423,
    "activeType": "add",
    "x-type": "roomEvent"
  },
  "pushTime": 1683248394513
}
```

> 删除

- 需要触发长链接的API：`/v3/devices/resources/group/{groupId}`

- 长链接推送数据格式

```json
{
  "pushType": 3,
  "badge": 0,
  "id": "1654289784546631680",
  "alert": "",
  "ext": {
    "familyId": 11838,
    "roomId": 3423,
    "activeType": "delete",
    "x-type": "roomEvent"
  },
  "pushTime": 1683248394513
}
```

> 扩展字段变更

- 需要触发长链接的API：`/v3/devices/resources/group/{groupId}?ignoreMembers=true`

- 长链接推送数据格式

```json
{
  "pushType": 3,
  "badge": 0,
  "id": "1654289784546631680",
  "alert": "",
  "ext": {
    "familyId": 11838,
    "roomId": 3423,
    "activeType": "stateChanged",
    "x-type": "roomEvent"
  },
  "pushTime": 1683248394513
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
  "ext": {
    "deviceSerial": "LDV_MESH_TEMPERATURE_DEVICE:5B8F6615FA68EE31829F23538ABF97C9",
    "familyId": 2345,
    "roomId": 54466,
    "activeType": "addDevice",
    "userId": "75caa57b8ecd4db88e7f30486b7acc93",
    "version": "v3",
    "x-type": "userDevEvent"
  },
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
  "id": "1654291527078617088",
  "alert": "",
  "ext": {
    "deviceSerial": "LDV_MESH_TEMPERATURE_DEVICE:5B8F6615FA68EE31829F23538ABF97C9",
    "familyId": 2345,
    "roomId": 54466,
    "activeType": "delDevice",
    "userId": "75caa57b8ecd4db88e7f30486b7acc93",
    "version": "v3",
    "x-type": "userDevEvent"
  },
  "pushTime": 1683248809963
}
```
