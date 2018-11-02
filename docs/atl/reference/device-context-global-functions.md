---
title: デバイス コンテキストに関するグローバル関数
ms.date: 11/04/2016
f1_keywords:
- atlwin/ATL::AtlCreateTargetDC
ms.assetid: 08ec28f6-daff-4882-9544-e8a4639d05c4
ms.openlocfilehash: 25ceae897d3cc845ab06fd4d898c87518b15eacb
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50551204"
---
# <a name="device-context-global-functions"></a>デバイス コンテキストに関するグローバル関数

この関数は、特定のデバイスのデバイス コンテキストを作成します。

|||
|-|-|
|[AtlCreateTargetDC](#atlcreatetargetdc)|デバイス コンテキストを作成します。|

##  <a name="atlcreatetargetdc"></a>  AtlCreateTargetDC

指定されたデバイスのデバイス コンテキストを作成、 [DVTARGETDEVICE](/windows/desktop/api/objidl/ns-objidl-tagdvtargetdevice)構造体。

```
HDC AtlCreateTargetDC(HDC hdc, DVTARGETDEVICE* ptd);
```

### <a name="parameters"></a>パラメーター

*hdc*<br/>
[in]デバイス コンテキスト、または NULL の既存のハンドル。

*ptd*<br/>
[in]ポインター、`DVTARGETDEVICE`対象デバイスに関する情報を含む構造体。

### <a name="return-value"></a>戻り値

指定されたデバイスのデバイス コンテキストへのハンドルを返します、`DVTARGETDEVICE`します。 デバイスが指定されていない場合は、既定のディスプレイ デバイスにハンドルを返します。

### <a name="remarks"></a>Remarks

構造体が NULL の場合と*hdc*が NULL で、既定のディスプレイ デバイスのデバイス コンテキストを作成します。

場合*hdc*が NULL でないと*ptd*が null の場合、既存の関数を返します*hdc*します。

## <a name="requirements"></a>必要条件

**ヘッダー:** atlwin.h

## <a name="see-also"></a>関連項目

[関数](../../atl/reference/atl-functions.md)
