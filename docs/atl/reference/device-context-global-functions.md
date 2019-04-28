---
title: デバイス コンテキストに関するグローバル関数
ms.date: 11/04/2016
f1_keywords:
- atlwin/ATL::AtlCreateTargetDC
ms.assetid: 08ec28f6-daff-4882-9544-e8a4639d05c4
ms.openlocfilehash: aeebec65def9364e56156f6bb323815da012e11f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62276563"
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
