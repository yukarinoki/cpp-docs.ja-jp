---
title: _AtlCreateWndData 構造 |Microsoft ドキュメント
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
ms.openlocfilehash: cc8bf88ce5258dc36a06f32ebaa5e2cdf15092fc
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="atlcreatewnddata-structure"></a>_AtlCreateWndData 構造体
この構造体には、ATL の windowing コードのクラス インスタンス データが含まれています。  
  
## <a name="syntax"></a>構文  
  
```
    struct _AtlCreateWndData{
    void* m_pThis;
    DWORD m_dwThreadID;
    _AtlCreateWndData* m_pNext;
};
```  
  
## <a name="members"></a>メンバー  
 **m_pThis**  
 **この**ポインターをウィンドウ プロシージャに、クラスのインスタンスへのアクセスを取得するために使用します。  
  
 `m_dwThreadID`  
 現在のクラス インスタンスのスレッド ID。  
  
 **m_pNext**  
 次へのポインター`_AtlCreateWndData`オブジェクト。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlbase.h  
  
## <a name="see-also"></a>関連項目  
 [構造体](../../atl/reference/atl-structures.md)





