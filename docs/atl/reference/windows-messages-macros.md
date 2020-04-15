---
title: ウィンドウズメッセージマクロ
ms.date: 11/04/2016
f1_keywords:
- atlbase/ATL::WM_FORWARDMSG
ms.assetid: 63abd22c-372d-4148-bb04-c605950ae64f
ms.openlocfilehash: a5a6d45c64d6123128ae362c1ef5643392439f41
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329410"
---
# <a name="windows-messages-macros"></a>ウィンドウズメッセージマクロ

このマクロはウィンドウ メッセージを転送します。

|||
|-|-|
|[WM_FORWARDMSG](#wm_forwardmsg)|ウィンドウが受信したメッセージを別のウィンドウに転送して処理するために使用します。|

## <a name="requirements"></a>必要条件

**ヘッダー:** atlbase.h

## <a name="wm_forwardmsg"></a><a name="wm_forwardmsg"></a>WM_FORWARDMSG

このマクロは、ウィンドウが受信したメッセージを別のウィンドウに転送して処理します。

```
WM_FORWARDMSG
```

### <a name="return-value"></a>戻り値

メッセージが処理された場合は 0 以外、処理されない場合は 0 以外の値を返します。

### <a name="remarks"></a>解説

WM_FORWARDMSGを使用して、ウィンドウが受信したメッセージを別のウィンドウに転送して処理します。 LPARAM および WPARAM パラメーターは、次のように使用されます。

|パラメーター|使用法|
|---------------|-----------|
|Wparam|ユーザーが定義するデータ|
|Lparam|メッセージに関する`MSG`情報を含む構造体へのポインター|

### <a name="example"></a>例

次の例では、`m_hWndOther`このメッセージを受信する他のウィンドウを表します。

[!code-cpp[NVC_ATL_Windowing#137](../../atl/codesnippet/cpp/windows-messages-macros_1.cpp)]

## <a name="see-also"></a>関連項目

[マクロ](../../atl/reference/atl-macros.md)
