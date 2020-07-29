---
title: _AtlCreateWndData 構造体
ms.date: 11/04/2016
f1_keywords:
- ATL::_AtlCreateWndData
- ATL._AtlCreateWndData
- _AtlCreateWndData
helpviewer_keywords:
- _AtlCreateWndData structure
- AtlCreateWndData structure
ms.assetid: 76ed5382-bfbf-4b8b-8a29-912688dfd2ae
ms.openlocfilehash: a38ddb7e3575e883c11b14a9b01004bb54fcd4a4
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87230014"
---
# <a name="_atlcreatewnddata-structure"></a>_AtlCreateWndData 構造体

この構造体は、ATL のウィンドウ化コードにクラスインスタンスデータを格納します。

## <a name="syntax"></a>構文

```cpp
    struct _AtlCreateWndData{
    void* m_pThis;
    DWORD m_dwThreadID;
    _AtlCreateWndData* m_pNext;
};
```

## <a name="members"></a>メンバー

`m_pThis`<br/>
**`this`** ウィンドウプロシージャでクラスインスタンスにアクセスするために使用されるポインター。

`m_dwThreadID`<br/>
現在のクラスインスタンスのスレッド ID。

`m_pNext`<br/>
次のオブジェクトへのポインター `_AtlCreateWndData` 。

## <a name="requirements"></a>必要条件

**ヘッダー:** atlbase. h

## <a name="see-also"></a>関連項目

[クラスと構造体](../../atl/reference/atl-classes.md)
