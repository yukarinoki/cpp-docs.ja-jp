---
description: '詳細情報: _ATL_BASE_MODULE70 構造'
title: _ATL_BASE_MODULE70 構造体
ms.date: 11/04/2016
f1_keywords:
- ATL::_ATL_BASE_MODULE70
- ATL._ATL_BASE_MODULE70
- _ATL_BASE_MODULE70
helpviewer_keywords:
- ATL_BASE_MODULE70 structure
- _ATL_BASE_MODULE70 structure
ms.assetid: 4539282f-15b8-4d7c-aafa-a85dc56f4980
ms.openlocfilehash: 5bcf2083f9c8991871c05535fd3e20a39bfeb822
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97165512"
---
# <a name="_atl_base_module70-structure"></a>_ATL_BASE_MODULE70 構造体

ATL を使用するすべてのプロジェクトで使用されます。

## <a name="syntax"></a>構文

```cpp
struct _ATL_BASE_MODULE70 {
    UINT cbSize;
    HINSTANCE m_hInst;
    HINSTANCE m_hInstResource;
    bool m_bNT5orWin98;
    DWORD dwAtlBuildVer;
    GUID* pguidVer;
    CRITICAL_SECTION m_csResource;
    CSimpleArray<HINSTANCE> m_rgResourceInstance;
};
```

## <a name="members"></a>メンバー

`cbSize`<br/>
構造体のサイズ。バージョン管理に使用されます。

`m_hInst`<br/>
`hInstance`このモジュールの (exe または dll のいずれか)。

`m_hInstResource`<br/>
既定のインスタンスリソースハンドル。

`m_bNT5orWin98`<br/>
オペレーティングシステムのバージョン情報。 ATL によって内部的に使用されます。

`dwAtlBuildVer`<br/>
ATL のバージョンを格納します。 現在、0x0700 です。

`pguidVer`<br/>
ATL の内部 GUID。

`m_csResource`<br/>
配列へのアクセスを同期するために使用 `m_rgResourceInstance` します。 ATL によって内部的に使用されます。

`m_rgResourceInstance`<br/>
ATL が認識しているすべてのリソースインスタンス内のリソースを検索するために使用される配列。 ATL によって内部的に使用されます。

## <a name="remarks"></a>解説

[_ATL_BASE_MODULE](atl-typedefs.md#_atl_base_module) は _ATL_BASE_MODULE70 の typedef として定義されます。

## <a name="requirements"></a>要件

**ヘッダー:** atlcore .h

## <a name="see-also"></a>関連項目

[クラスと構造体](../../atl/reference/atl-classes.md)
