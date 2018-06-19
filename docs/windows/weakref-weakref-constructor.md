---
title: Weakref::weakref コンス トラクター |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::WeakRef::WeakRef
dev_langs:
- C++
helpviewer_keywords:
- WeakRef, constructor
ms.assetid: 589f87e0-8dcc-4e82-aab2-f2f66f1ec47c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ae70dabdd86fedf82c26c0c7d9a09d842e2310e7
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33891049"
---
# <a name="weakrefweakref-constructor"></a>WeakRef::WeakRef コンストラクター
WeakRef クラスの新しいインスタンスを初期化します。  
  
## <a name="syntax"></a>構文  
  
```  
WeakRef();  
WeakRef(  
   decltype(__nullptr)  
);  
  
WeakRef(  
   _In_opt_ IWeakReference* ptr  
);  
  
WeakRef(  
   const ComPtr<IWeakReference>& ptr  
);  
  
WeakRef(  
   const WeakRef& ptr  
);  
  
WeakRef(  
   _Inout_ WeakRef&& ptr  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `ptr`  
 ポインター、参照、または現在の WeakRef オブジェクトを初期化する既存のオブジェクトへの右辺値参照。  
  
## <a name="remarks"></a>コメント  
 最初のコンス トラクターは、空の WeakRef オブジェクトを初期化します。 2 番目のコンス トラクターは、IWeakReference インターフェイスへのポインターから WeakRef オブジェクトを初期化します。 3 番目のコンス トラクターが ComPtr への参照から WeakRef オブジェクトを初期化します\<IWeakReference > オブジェクト。 4 番目と 5 番目のコンス トラクターは、別の WeakRef オブジェクトから WeakRef オブジェクトを初期化します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** client.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>関連項目  
 [WeakRef クラス](../windows/weakref-class.md)