---
title: ミュー テックス Class1 |Microsoft Docs
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
ms.openlocfilehash: cd9c3dbbcbffff32f7c1611b6b49ee19ada7e52c
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2018
ms.locfileid: "39606775"
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
|`SyncLock`|同期ロックをサポートするクラスのシノニムです。|  
  
### <a name="public-constructor"></a>パブリック コンス トラクター  
  
|name|説明|  
|----------|-----------------|  
|[Mutex::Mutex コンストラクター](../windows/mutex-mutex-constructor.md)|新しいインスタンスを初期化、**ミュー テックス**クラス。|  
  
### <a name="public-members"></a>パブリック メンバー  
  
|name|説明|  
|----------|-----------------|  
|[Mutex::Lock メソッド](../windows/mutex-lock-method.md)|現在のオブジェクトまでの待機、または**ミュー テックス**リリース ミュー テックス、または指定されたタイムアウト期間が経過した、指定したハンドルに関連付けられているオブジェクト。|  
  
### <a name="public-operator"></a>パブリック演算子  
  
|name|説明|  
|----------|-----------------|  
|[Mutex::operator= 演算子](../windows/mutex-operator-assign-operator.md)|割り当て (移動)、指定した**ミュー テックス**現在オブジェクト**ミュー テックス**オブジェクト。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `Mutex`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>関連項目  
 [Microsoft::WRL::Wrappers 名前空間](../windows/microsoft-wrl-wrappers-namespace.md)