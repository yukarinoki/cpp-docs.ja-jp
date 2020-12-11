---
description: '詳細情報: _AtlCreateWndData 構造'
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
ms.openlocfilehash: 912f2d108baa9cae1b91a34f3c5e386339d11f0b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97158609"
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

## <a name="requirements"></a>要件

**ヘッダー:** atlbase. h

## <a name="see-also"></a>関連項目

[クラスと構造体](../../atl/reference/atl-classes.md)
