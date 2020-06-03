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
ms.openlocfilehash: 6453156a59b73bcb06c7c86920e1dc524874cef8
ms.sourcegitcommit: 2bc15c5b36372ab01fa21e9bcf718fa22705814f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2020
ms.locfileid: "82168541"
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
**この**ポインターは、ウィンドウプロシージャでクラスインスタンスにアクセスするために使用されます。

`m_dwThreadID`<br/>
現在のクラスインスタンスのスレッド ID。

`m_pNext`<br/>
次`_AtlCreateWndData`のオブジェクトへのポインター。

## <a name="requirements"></a>必要条件

**ヘッダー:** atlbase. h

## <a name="see-also"></a>関連項目

[クラスと構造体](../../atl/reference/atl-classes.md)
