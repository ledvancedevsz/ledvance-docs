# 萤石长链接API `1.0.1`

---

### 1. 家庭新增/删除

> 新增

- 需要触发长链接的API：`/v3/family/sync/batchAdd` `/v3/family/add`

- 期望长链接推送数据格式

```json
{
  "id": "1658318781516718888",
  "alert": "",
  "pushTime": 1682301633612,
  "type": "familyAdd",
  "ext": {
    "familyId": 1234
  }
}
```

> 删除

- 需要触发长链接的API：`/v3/family/{familyId}/delete`

- 期望长链接推送数据格式

```json
{
  "id": "1658318781516718888",
  "alert": "",
  "pushTime": 1682301633612,
  "type": "familyDel",
  "ext": {
    "familyId": 1234
  }
}
```

### 2. 房间新增/删除/扩展字段变更

> 新增

- 需要触发长链接的API：`/v3/family/sync/batchAdd` `/v3/devices/resources/group`

- 期望长链接推送数据格式

```json
{
  "id": "1658318781516718888",
  "alert": "",
  "pushTime": 1682301633612,
  "type": "roomAdd",
  "ext": {
    "familyId": 1234,
    "roomId": 1234
  }
}
```

> 删除

- 需要触发长链接的API：`/v3/devices/resources/group/{groupId}`

- 期望长链接推送数据格式

```json
{
  "id": "1658318781516718888",
  "alert": "",
  "pushTime": 1682301633612,
  "type": "roomDel",
  "ext": {
    "familyId": 1234,
    "roomId": 1234
  }
}
```

> 扩展字段变更

- 需要触发长链接的API：`/v3/devices/resources/group/{groupId}?ignoreMembers=true`

- 期望长链接推送数据格式

```json
{
  "id": "1658318781516718888",
  "alert": "",
  "pushTime": 1682301633612,
  "type": "roomStateChanged",
  "ext": {
    "familyId": 1234,
    "roomId": 1234
  }
}
```

### 3. 设备新增/删除

> 新增

- 需要触发长链接的API：`/v3/devices/sync/batchAdd` `/v3/devices/sync/add`

- 期望长链接推送数据格式

```json
{
  "id": "1658318781516718888",
  "alert": "",
  "pushTime": 1682301633612,
  "type": "deviceAdd",
  "ext": {
    "familyId": 1234,
    "deviceId": "TY_LDV_w2oq3xw6qdrfpzrc:bf3309e966ff0bec0fzl8y"
  }
}
```

> 删除

- 需要触发长链接的API：`v3/devices/sync/{deviceId}`

- 期望长链接推送数据格式

```json
{
  "id": "1658318781516718888",
  "alert": "",
  "pushTime": 1682301633612,
  "type": "deviceDel",
  "ext": {
    "familyId": 1234,
    "deviceId": "TY_LDV_w2oq3xw6qdrfpzrc:bf3309e966ff0bec0fzl8y"
  }
}
```