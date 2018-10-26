---
title: _ATL_WIN_MODULE70 構造体 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- _ATL_WIN_MODULE70
- ATL::_ATL_WIN_MODULE70
- ATL._ATL_WIN_MODULE70
dev_langs:
- C++
helpviewer_keywords:
- _ATL_WIN_MODULE70 structure
- ATL_WIN_MODULE70 structure
ms.assetid: a0aaf3ea-ca77-46ec-bd53-4dfb61dffbea
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: dcb66d55f1d75d584414c0273882a5424fe72650
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50064824"
---
# <a name="atlwinmodule70-structure"></a>_ATL_WIN_MODULE70 構造体

ATL でウィンドウ作成コードで使用されます。

## <a name="syntax"></a>構文

```
struct _ATL_WIN_MODULE70 {
    UNIT cbSize;
    CRITICAL_SECTION m_csWindowCreate;
    _AtlCreateWndData* m_pCreateWndList;
    CSimpleArray<ATOM> m_rgWindowClassAtoms;
};
```

## <a name="members"></a>メンバー

`cbSize`<br/>
バージョン管理に使用される、構造のサイズ。

`m_csWindowCreate`<br/>
ウィンドウの登録コードへのアクセスをシリアル化するために使用します。 ATL で内部的に使用

`m_pCreateWndList`<br/>
Windows をそれらのオブジェクトにバインドするために使用します。 ATL で内部的に使用

`m_rgWindowClassAtoms`<br/>
終了時に正しく登録それらができるように、ウィンドウ クラスの登録を追跡するために使用します。 ATL で内部的に使用

## <a name="remarks"></a>Remarks

[_ATL_WIN_MODULE](atl-typedefs.md#_atl_win_module)の typedef として定義されて`_ATL_WIN_MODULE70`します。

## <a name="requirements"></a>必要条件

**ヘッダー:** atlbase.h

## <a name="see-also"></a>関連項目

[クラスと構造体](../../atl/reference/atl-classes.md)

