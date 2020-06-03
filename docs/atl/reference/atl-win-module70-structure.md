---
title: _ATL_WIN_MODULE70 構造体
ms.date: 11/04/2016
f1_keywords:
- _ATL_WIN_MODULE70
- ATL::_ATL_WIN_MODULE70
- ATL._ATL_WIN_MODULE70
helpviewer_keywords:
- _ATL_WIN_MODULE70 structure
- ATL_WIN_MODULE70 structure
ms.assetid: a0aaf3ea-ca77-46ec-bd53-4dfb61dffbea
ms.openlocfilehash: 770e78e4ad87338528aa654f5ecaa08b45315846
ms.sourcegitcommit: 2bc15c5b36372ab01fa21e9bcf718fa22705814f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2020
ms.locfileid: "82168554"
---
# <a name="_atl_win_module70-structure"></a>_ATL_WIN_MODULE70 構造体

ATL のウィンドウコードによって使用されます。

## <a name="syntax"></a>構文

```cpp
struct _ATL_WIN_MODULE70 {
    UNIT cbSize;
    CRITICAL_SECTION m_csWindowCreate;
    _AtlCreateWndData* m_pCreateWndList;
    CSimpleArray<ATOM> m_rgWindowClassAtoms;
};
```

## <a name="members"></a>メンバー

`cbSize`<br/>
構造体のサイズ。バージョン管理に使用されます。

`m_csWindowCreate`<br/>
ウィンドウ登録コードへのアクセスをシリアル化するために使用されます。 ATL によって内部的に使用されます。

`m_pCreateWndList`<br/>
ウィンドウをオブジェクトにバインドするために使用します。 ATL によって内部的に使用されます。

`m_rgWindowClassAtoms`<br/>
終了時に適切に登録解除できるように、ウィンドウクラスの登録を追跡するために使用されます。 ATL によって内部的に使用されます。

## <a name="remarks"></a>解説

[_ATL_WIN_MODULE](atl-typedefs.md#_atl_win_module)は、の`_ATL_WIN_MODULE70`typedef として定義されます。

## <a name="requirements"></a>必要条件

**ヘッダー:** atlbase. h

## <a name="see-also"></a>関連項目

[クラスと構造体](../../atl/reference/atl-classes.md)
