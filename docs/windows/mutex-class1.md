---
title: ミュー テックス Class1 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Mutex
dev_langs:
- C++
helpviewer_keywords:
- Mutex class
ms.assetid: 682a0963-721c-46a2-8871-000e9997505b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9a9e9674dd8ac5aa7d444a77df66c1aff4a70299
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="mutex-class1"></a>ミュー テックス Class1
共有リソースを排他的に制御する同期オブジェクトを表します。  
  
## <a name="syntax"></a>構文  
  
```  
class Mutex : public HandleT<HandleTraits::MutexTraits>  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-typedefs"></a>パブリック typedef  
  
|名前|説明|  
|----------|-----------------|  
|**SyncLock**|同期ロックをサポートするクラスのシノニムです。|  
  
### <a name="public-constructor"></a>パブリック コンス トラクター  
  
|名前|説明|  
|----------|-----------------|  
|[Mutex::Mutex コンストラクター](../windows/mutex-mutex-constructor.md)|Mutex クラスの新しいインスタンスを初期化します。|  
  
### <a name="public-members"></a>パブリック メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[Mutex::Lock メソッド](../windows/mutex-lock-method.md)|ミュー テックスを解放するまで、現在のオブジェクト、または、指定したハンドルに関連付けられているミュー テックス オブジェクト待機または指定されたタイムアウト期間が経過しました。|  
  
### <a name="public-operator"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[Mutex::operator= 演算子](../windows/mutex-operator-assign-operator.md)|割り当て (移動)、指定されたミュー テックスは、現在のミュー テックス オブジェクトをオブジェクトです。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `Mutex`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>関連項目  
 [Microsoft::WRL::Wrappers 名前空間](../windows/microsoft-wrl-wrappers-namespace.md)