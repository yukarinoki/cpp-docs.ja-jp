---
description: '詳細情報: _ATL_WIN_MODULE70 構造'
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
ms.openlocfilehash: 11b7fdad71fa8c7b615a0e6873571c38420c9b5d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97158622"
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

[_ATL_WIN_MODULE](atl-typedefs.md#_atl_win_module) は、の typedef として定義され `_ATL_WIN_MODULE70` ます。

## <a name="requirements"></a>要件

**ヘッダー:** atlbase. h

## <a name="see-also"></a>関連項目

[クラスと構造体](../../atl/reference/atl-classes.md)
