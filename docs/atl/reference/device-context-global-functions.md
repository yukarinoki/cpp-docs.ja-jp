---
title: デバイスコンテキストのグローバル関数
ms.date: 11/04/2016
f1_keywords:
- atlwin/ATL::AtlCreateTargetDC
ms.assetid: 08ec28f6-daff-4882-9544-e8a4639d05c4
ms.openlocfilehash: d2d25660083f074683a3f42f878497ce14a008b8
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88833466"
---
# <a name="device-context-global-functions"></a>デバイスコンテキストのグローバル関数

この関数は、特定のデバイスのデバイスコンテキストを作成します。

|名前|説明|
|-|-|
|[AtlCreateTargetDC](#atlcreatetargetdc)|デバイスコンテキストを作成します。|

## <a name="atlcreatetargetdc"></a><a name="atlcreatetargetdc"></a> AtlCreateTargetDC

[DVTARGETDEVICE](/windows/win32/api/objidl/ns-objidl-dvtargetdevice)構造体で指定されたデバイスのデバイスコンテキストを作成します。

```
HDC AtlCreateTargetDC(HDC hdc, DVTARGETDEVICE* ptd);
```

### <a name="parameters"></a>パラメーター

*hdc*<br/>
からデバイスコンテキストの既存のハンドル、または NULL。

*ptd*<br/>
から `DVTARGETDEVICE` ターゲットデバイスに関する情報を格納している構造体へのポインター。

### <a name="return-value"></a>戻り値

で指定されたデバイスのデバイスコンテキストを示すハンドルを返し `DVTARGETDEVICE` ます。 デバイスが指定されていない場合は、既定の表示デバイスへのハンドルを返します。

### <a name="remarks"></a>解説

構造体が NULL で、 *hdc* が null の場合、は既定の表示デバイスのデバイスコンテキストを作成します。

*Hdc*が null でなく、 *ptd*が null の場合、関数は既存の*hdc*を返します。

## <a name="requirements"></a>必要条件

**ヘッダー:** atlwin. h

## <a name="see-also"></a>関連項目

[関数](../../atl/reference/atl-functions.md)
