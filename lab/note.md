# 解析格式

## RPG Maker MZ (NTR聖女騎士レイア)

### Note

- 條件選項 ("en(v[87]>=1&&s[3])ストーリー２")
- 變數帶入文本 ("%1は倒れた！")

#### Regular Expression Split

```py
import re

# 測試字串
text = "en(v[87]>=1&&s[3])ストーリー２"

# 使用正則表達式來分離條件與選項名稱
match = re.match(r"en\((.*?)\)(.+)", text)

if match:
    condition = match.group(1)  # 抓取括號內的條件
    choice_text = match.group(2)  # 括號後的選項名稱
    print("條件:", condition)
    print("選項名稱:", choice_text)
else:
    print("未匹配到條件")
```

### Actors.json

n > 0

- $.[n].name: 名稱
- $.[n].nickname: 綽號
- $.[n].profile: 簡介

### Animations.json

n > 0

- $.[n].name: 名稱

### Armors.json

n > 0

- $.[n].name: 名稱
- $.[n].description: 描述

### Classes.json

n > 0

- $.[n].name: 名稱

### CommonEvents.json

n > 0

- $.[n].name: 名稱
- $.[n].list[m].parameters: 角色對話 (where .code == 401)
- $.[n].list[m].parameters[3]: 說話角色 (where .code == 101)
- $.[n].list[m].parameters[1]: 選擇的選項 (where .code == 402)
- $.[n].list[m].parameters[0].parameters[0]: (list)所有選項 (where .code == 102)

### Enemies.json

n > 0

- $.[n].name: 名稱
- $.[n].note: 描述

### Items.json

n > 0

- $.[n].name: 名稱
- $.[n].description: 描述
- $.[n].note: 描述

### MapXXX.json

n > 0

- $.displayName: 地圖名稱
- $.events[n].name: 名稱
- $.events[n].note: 描述
- $.events[n].pages[m].list[o].parameters: 角色對話 (where .id == 401)
- $.events[n].pages[m].list[o].parameters[3]: 說話角色 (where .id == 101)
- $.events[n].pages[m].list[o].parameters[1]: 選擇的選項 (where .id == 402)
- $.events[n].pages[m].list[o].parameters[0].parameters[0]: (list)所有選項 (where .id == 102)

### MapInfos.json

n > 0

- $.[n].name: 名稱

### Skills.json

n > 0

- $.[n].name: 名稱
- $.[n].description: 描述

### States.json

n > 0

- $.[n].name: 名稱
- $.[n].note: 描述
- $.[n].message1: 狀態變更時的訊息
- $.[n].message2: 狀態變更時的訊息
- $.[n].message3: 狀態變更時的訊息
- $.[n].message4: 狀態變更時的訊息

### System.json

- $.gameTitle: 遊戲名稱
- $.armorTypes[n]: 裝備類型
- $.elements[n]: 屬性
- $.equipTypes[n]: 裝備類型
- $.skillTypes[n]: 技能類型
- $.switches[n]: 開關
- $.variables[n]: 變數

### Tilesets.json

n > 0

- $.[n].name: 名稱

### Troops.json

n > 0

- $.[n].name: 名稱

### Weapons.json

n > 0

- $.[n].name: 名稱
- $.[n].description: 描述
- $.[n].note: 描述