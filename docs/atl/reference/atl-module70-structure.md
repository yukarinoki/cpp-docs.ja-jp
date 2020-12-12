---
description: '詳細情報: _ATL_MODULE70 構造'
title: _ATL_MODULE70 構造体
ms.date: 11/04/2016
f1_keywords:
- _ATL_MODULE70
- ATL::_ATL_MODULE70
- ATL._ATL_MODULE70
helpviewer_keywords:
- ATL_MODULE70 structure
- _ATL_MODULE70 structure
ms.assetid: b059b2c8-dfd1-4ac9-b07d-39df638cc7b3
ms.openlocfilehash: 8a3076cebe7cab2bce49f660e8198052af393024
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97165356"
---
# <a name="_atl_module70-structure"></a>_ATL_MODULE70 構造体

すべての ATL モジュールで使用されるデータを格納します。

## <a name="syntax"></a>構文

```cpp
struct _ATL_MODULE70 {
    UINT cbSize;
    LONG m_nLockCnt;
    _ATL_TERMFUNC_ELEM* m_pTermFuncs;
    CComCriticalSection m_csStaticDataInitAndTypeInfo;
};
```

## <a name="members"></a>メンバー

`cbSize`<br/>
構造体のサイズ。バージョン管理に使用されます。

`m_nLockCnt`<br/>
モジュールを維持する期間を決定する参照カウント。

`m_pTermFuncs`<br/>
ATL がシャットダウンしたときに呼び出されるように登録されている関数を追跡します。

`m_csStaticDataInitAndTypeInfo`<br/>
マルチスレッドの状況で内部データへのアクセスを調整するために使用されます。

## <a name="remarks"></a>解説

[_ATL_MODULE](atl-typedefs.md#_atl_module) は、の typedef として定義され `_ATL_MODULE70` ます。

## <a name="requirements"></a>要件

**ヘッダー:** atlbase. h

## <a name="see-also"></a>関連項目

[クラスと構造体](../../atl/reference/atl-classes.md)
