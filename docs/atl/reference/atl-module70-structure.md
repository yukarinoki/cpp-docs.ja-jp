---
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
ms.openlocfilehash: 8d39cdd281e09cdfe09546627aa630a11d12464e
ms.sourcegitcommit: 2bc15c5b36372ab01fa21e9bcf718fa22705814f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2020
ms.locfileid: "82168567"
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

[_ATL_MODULE](atl-typedefs.md#_atl_module)は、の`_ATL_MODULE70`typedef として定義されます。

## <a name="requirements"></a>必要条件

**ヘッダー:** atlbase. h

## <a name="see-also"></a>関連項目

[クラスと構造体](../../atl/reference/atl-classes.md)
