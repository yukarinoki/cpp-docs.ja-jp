---
title: CComAutoDeleteCriticalSection クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComAutoDeleteCriticalSection
- atlcore/ATL::CComAutoDeleteCriticalSection
dev_langs:
- C++
helpviewer_keywords:
- CComAutoDeleteCriticalSection class
ms.assetid: 2396dbea-1c60-4841-b50e-c4e18af311a3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c5153520b5a5648f8352465031264c223ffd97c4
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32360065"
---
# <a name="ccomautodeletecriticalsection-class"></a>CComAutoDeleteCriticalSection クラス
このクラスは、取得し、クリティカル セクション オブジェクトの所有権を解放するためのメソッドを提供します。  
  
## <a name="syntax"></a>構文  
  
```
class CComAutoDeleteCriticalSection : public CComSafeDeleteCriticalSection
```  
  
## <a name="remarks"></a>コメント  
 `CComAutoDeleteCriticalSection` クラスから派生[CComSafeDeleteCriticalSection](../../atl/reference/ccomsafedeletecriticalsection-class.md)です。 ただし、`CComAutoDeleteCriticalSection`よりも優先、[用語](ccomsafedeletecriticalsection-class.md#term)メソッドを`private`アクセスで、強制的にだけこのクラスのインスタンスのスコープ外に出るまたは明示的に削除されたときメモリから発生する内部メモリ クリーンアップします。  

  
 このクラスは、その基本クラス経由で追加のメソッドを導入なしします。 参照してください[CComSafeDeleteCriticalSection](../../atl/reference/ccomsafedeletecriticalsection-class.md)と[CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)詳細については、クリティカル セクションのヘルパー クラス。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)  
  
 [CComSafeDeleteCriticalSection](../../atl/reference/ccomsafedeletecriticalsection-class.md)  
  
 `CComAutoDeleteCriticalSection`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlcore.h  
  
## <a name="see-also"></a>関連項目  
 [CComSafeDeleteCriticalSection クラス](../../atl/reference/ccomsafedeletecriticalsection-class.md)   
 [CComCriticalSection クラス](../../atl/reference/ccomcriticalsection-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)
