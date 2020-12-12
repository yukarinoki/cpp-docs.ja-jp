---
description: '詳細情報: _ATL_COM_MODULE70 構造'
title: _ATL_COM_MODULE70 構造体
ms.date: 11/04/2016
f1_keywords:
- ATL::_ATL_COM_MODULE70
- ATL._ATL_COM_MODULE70
- _ATL_COM_MODULE70
helpviewer_keywords:
- _ATL_COM_MODULE70 structure
- ATL_COM_MODULE70 structure
ms.assetid: 5b0b2fd0-bdeb-4c7e-8870-78fa69ace6e6
ms.openlocfilehash: db2139d1c816c13e6da104f6a6d785ef35a07721
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97165409"
---
# <a name="_atl_com_module70-structure"></a>_ATL_COM_MODULE70 構造体

ATL の COM 関連コードによって使用されます。

## <a name="syntax"></a>構文

```cpp
struct _ATL_COM_MODULE70 {
    UINT cbSize;
    HINSTANCE m_hInstTypeLib;
    _ATL_OBJMAP_ENTRY** m_ppAutoObjMapFirst;
    _ATL_OBJMAP_ENTRY** m_ppAutoObjMapLast;
    CRITICAL_SECTION m_csObjMap;
};
```

## <a name="members"></a>メンバー

`cbSize`<br/>
構造体のサイズ。バージョン管理に使用されます。

`m_hInstTypeLib`<br/>
このモジュールのタイプライブラリへのハンドルインスタンス。

`m_ppAutoObjMapFirst`<br/>
このモジュールのオブジェクトマップエントリの先頭を示す配列要素のアドレス。

`m_ppAutoObjMapLast`<br/>
このモジュールのオブジェクトマップエントリの末尾を示す配列要素のアドレス。

`m_csObjMap`<br/>
オブジェクトマップエントリへのアクセスをシリアル化するためのクリティカルセクション。 ATL によって内部的に使用されます。

## <a name="remarks"></a>解説

[_ATL_COM_MODULE](atl-typedefs.md#_atl_com_module) は _ATL_COM_MODULE70 の typedef として定義されます。

## <a name="requirements"></a>要件

**ヘッダー:** atlbase. h

## <a name="see-also"></a>関連項目

[クラスと構造体](../../atl/reference/atl-classes.md)
