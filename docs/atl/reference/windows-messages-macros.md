---
title: Windows メッセージに関するマクロ |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- atlbase/ATL::WM_FORWARDMSG
dev_langs:
- C++
ms.assetid: 63abd22c-372d-4148-bb04-c605950ae64f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3f9d312104254323e98f6b2fd031adf1064ecfac
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50078220"
---
# <a name="windows-messages-macros"></a>Windows メッセージに関するマクロ

このマクロは、ウィンドウ メッセージを転送します。

|||
|-|-|
|[WM_FORWARDMSG](#wm_forwardmsg)|処理するための別のウィンドウのウィンドウで受信メッセージの転送を使用します。|

## <a name="requirements"></a>必要条件

**ヘッダー:** atlbase.h

##  <a name="wm_forwardmsg"></a>  WM_FORWARDMSG

このマクロは、処理のための別のウィンドウのウィンドウで受信したメッセージを転送します。

```
WM_FORWARDMSG
```

### <a name="return-value"></a>戻り値

0 以外の場合、メッセージが処理された場合しない場合は 0。

### <a name="remarks"></a>Remarks

処理のための別のウィンドウのウィンドウで受信したメッセージを転送するのに WM_FORWARDMSG を使用します。 LPARAM および WPARAM パラメーターは、次のように使用されます。

|パラメーター|使用法|
|---------------|-----------|
|WPARAM|ユーザーによって定義されたデータ|
|LPARAM|ポインターを`MSG`メッセージに関する情報を含む構造体|

### <a name="example"></a>例

次の例では、`m_hWndOther`このメッセージを受信する他のウィンドウを表します。

[!code-cpp[NVC_ATL_Windowing#137](../../atl/codesnippet/cpp/windows-messages-macros_1.cpp)]

## <a name="see-also"></a>関連項目

[[マクロ]](../../atl/reference/atl-macros.md)
