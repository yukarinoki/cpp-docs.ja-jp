---
title: デバイス コンテキストのグローバル関数
ms.date: 11/04/2016
f1_keywords:
- atlwin/ATL::AtlCreateTargetDC
ms.assetid: 08ec28f6-daff-4882-9544-e8a4639d05c4
ms.openlocfilehash: e640f310a1976c29a39f0ab7c2575dfd1073c889
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81330153"
---
# <a name="device-context-global-functions"></a>デバイス コンテキストのグローバル関数

この関数は、指定されたデバイスのデバイス コンテキストを作成します。

|||
|-|-|
|[AtlCreateTargetDC](#atlcreatetargetdc)|デバイス コンテキストを作成します。|

## <a name="atlcreatetargetdc"></a><a name="atlcreatetargetdc"></a>アトル・ア・ラ・リスト・ア・ラ・ト

[DVTARGETDEVICE](/windows/win32/api/objidl/ns-objidl-dvtargetdevice)構造体で指定されたデバイスのデバイス コンテキストを作成します。

```
HDC AtlCreateTargetDC(HDC hdc, DVTARGETDEVICE* ptd);
```

### <a name="parameters"></a>パラメーター

*Hdc*<br/>
[in]デバイス コンテキストの既存のハンドル、または NULL。

*Ptd*<br/>
[in]ターゲット デバイスに`DVTARGETDEVICE`関する情報を格納する構造体へのポインター。

### <a name="return-value"></a>戻り値

で指定されたデバイスのデバイス コンテキストへのハンドルを返します`DVTARGETDEVICE`。 デバイスが指定されていない場合は、既定の表示デバイスへのハンドルを返します。

### <a name="remarks"></a>解説

構造体が NULL で *、hdc*が NULL の場合、既定の表示デバイスのデバイス コンテキストを作成します。

*hdc*が NULL で *、ptd*が NULL の場合、この関数は既存の*hdc*を返します。

## <a name="requirements"></a>必要条件

**ヘッダー:** atlwin.h

## <a name="see-also"></a>関連項目

[関数](../../atl/reference/atl-functions.md)
