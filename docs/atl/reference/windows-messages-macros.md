---
title: Windows メッセージのマクロ
ms.date: 11/04/2016
f1_keywords:
- atlbase/ATL::WM_FORWARDMSG
ms.assetid: 63abd22c-372d-4148-bb04-c605950ae64f
ms.openlocfilehash: b4cd3c2eea24449eb17050b147d9c59560d8358f
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88834441"
---
# <a name="windows-messages-macros"></a>Windows メッセージのマクロ

このマクロは、ウィンドウメッセージを転送します。

|名前|説明|
|-|-|
|[WM_FORWARDMSG](#wm_forwardmsg)|ウィンドウによって受信されたメッセージを別のウィンドウに転送して処理する場合に使用します。|

## <a name="requirements"></a>必要条件

**ヘッダー:** atlbase. h

## <a name="wm_forwardmsg"></a><a name="wm_forwardmsg"></a> WM_FORWARDMSG

このマクロは、ウィンドウによって受信されたメッセージを別のウィンドウに転送して処理します。

```
WM_FORWARDMSG
```

### <a name="return-value"></a>戻り値

メッセージが処理された場合は0以外の値。それ以外の場合は0。

### <a name="remarks"></a>解説

WM_FORWARDMSG を使用して、ウィンドウによって受信されたメッセージを別のウィンドウに転送して処理します。 LPARAM と WPARAM のパラメーターは次のように使用されます。

|パラメーター|使用法|
|---------------|-----------|
|WPARAM|ユーザーによって定義されたデータ|
|LPARAM|`MSG`メッセージに関する情報を格納している構造体へのポインター。|

### <a name="example"></a>例

次の例では、は、 `m_hWndOther` このメッセージを受信する他のウィンドウを表します。

[!code-cpp[NVC_ATL_Windowing#137](../../atl/codesnippet/cpp/windows-messages-macros_1.cpp)]

## <a name="see-also"></a>関連項目

[[マクロ]](../../atl/reference/atl-macros.md)
