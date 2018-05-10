---
title: ATL コレクションと列挙子クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- enumerators, ATL classes
- collection classes, ATL
ms.assetid: 6818db73-7094-48d8-a0ca-18147beec362
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a47525bb21b896b0fef8393cab66142ed40311ea
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="atl-collection-and-enumerator-classes"></a>ATL コレクションと列挙子クラス
ATL は、コレクションと列挙子を実装するのに役立つ次のクラスを提供します。  
  
|クラス|説明|  
|-----------|-----------------|  
|[ICollectionOnSTLImpl](../atl/reference/icollectiononstlimpl-class.md)|コレクション インターフェイスの実装|  
|[IEnumOnSTLImpl](../atl/reference/ienumonstlimpl-class.md)|列挙子インターフェイスの実装 (C++ 標準ライブラリと互換性のあるコンテナーに格納されたデータを想定)|  
|[CComEnumImpl](../atl/reference/ccomenumimpl-class.md)|列挙子インターフェイスの実装 (配列に格納されたデータを想定)|  
|[CComEnumOnSTL](../atl/reference/ccomenumonstl-class.md)|列挙子オブジェクトの実装 (を使用して`IEnumOnSTLImpl`)|  
|[CComEnum](../atl/reference/ccomenum-class.md)|列挙子オブジェクトの実装 (を使用して`CComEnumImpl`)|  
|[_Copy](../atl/atl-copy-policy-classes.md)|Policy クラスをコピーします。|  
|[_CopyInterface](../atl/atl-copy-policy-classes.md)|Policy クラスをコピーします。|  
|[CAdapt](../atl/reference/cadapt-class.md)|アダプター クラス (非表示に**演算子 (& a)** 許可`CComPtr`、 `CComQIPtr`、および`CComBSTR`C++ 標準ライブラリのコンテナーに格納される)|  
  
## <a name="see-also"></a>関連項目  
 [コレクションと列挙子](../atl/atl-collections-and-enumerators.md)

