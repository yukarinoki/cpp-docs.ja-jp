---
description: 詳細については、「デバイスコンテキストのグローバル関数」を参照してください。
title: デバイスコンテキストのグローバル関数
ms.date: 11/04/2016
f1_keywords:
- atlwin/ATL::AtlCreateTargetDC
ms.assetid: 08ec28f6-daff-4882-9544-e8a4639d05c4
ms.openlocfilehash: f5e87271170e29a2f0cc4d42b4e7739a5fd869ab
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97139907"
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

*Hdc* が null でなく、 *ptd* が null の場合、関数は既存の *hdc* を返します。

## <a name="requirements"></a>要件

**ヘッダー:** atlwin. h

## <a name="see-also"></a>関連項目

[関数](../../atl/reference/atl-functions.md)
