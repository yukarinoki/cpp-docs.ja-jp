---
title: _AtlCreateWndData 構造体 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- ATL::_AtlCreateWndData
- ATL._AtlCreateWndData
- _AtlCreateWndData
dev_langs:
- C++
helpviewer_keywords:
- _AtlCreateWndData structure
- AtlCreateWndData structure
ms.assetid: 76ed5382-bfbf-4b8b-8a29-912688dfd2ae
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 71c0fb14574aedb74d756e72a93cd0dc626ba086
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46057380"
---
# <a name="atlcreatewnddata-structure"></a>_AtlCreateWndData 構造体

この構造体には、ATL でウィンドウ作成コードのクラス インスタンスのデータが含まれています。

## <a name="syntax"></a>構文

```
    struct _AtlCreateWndData{
    void* m_pThis;
    DWORD m_dwThreadID;
    _AtlCreateWndData* m_pNext;
};
```

## <a name="members"></a>メンバー

`m_pThis`<br/>
**この**ポインターをウィンドウ プロシージャで、クラスのインスタンスへのアクセスを取得するために使用します。

`m_dwThreadID`<br/>
現在のクラス インスタンスのスレッド ID。

`m_pNext`<br/>
次へのポインター`_AtlCreateWndData`オブジェクト。

## <a name="requirements"></a>要件

**ヘッダー:** atlbase.h

## <a name="see-also"></a>関連項目

[クラスと構造体](../../atl/reference/atl-classes.md)

