---
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
ms.openlocfilehash: 3893e4ce4fcd24f48d9e981ad24505f82dc98833
ms.sourcegitcommit: 2bc15c5b36372ab01fa21e9bcf718fa22705814f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2020
ms.locfileid: "82168645"
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
この`hInstance`モジュールの (exe または dll のいずれか)。

`m_hInstResource`<br/>
既定のインスタンスリソースハンドル。

`m_bNT5orWin98`<br/>
オペレーティングシステムのバージョン情報。 ATL によって内部的に使用されます。

`dwAtlBuildVer`<br/>
ATL のバージョンを格納します。 現在、0x0700 です。

`pguidVer`<br/>
ATL の内部 GUID。

`m_csResource`<br/>
配列への`m_rgResourceInstance`アクセスを同期するために使用します。 ATL によって内部的に使用されます。

`m_rgResourceInstance`<br/>
ATL が認識しているすべてのリソースインスタンス内のリソースを検索するために使用される配列。 ATL によって内部的に使用されます。

## <a name="remarks"></a>解説

[_ATL_BASE_MODULE](atl-typedefs.md#_atl_base_module)は _ATL_BASE_MODULE70 の typedef として定義されます。

## <a name="requirements"></a>必要条件

**ヘッダー:** atlcore .h

## <a name="see-also"></a>関連項目

[クラスと構造体](../../atl/reference/atl-classes.md)
