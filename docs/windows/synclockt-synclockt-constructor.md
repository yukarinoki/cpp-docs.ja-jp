---
title: Synclockt::synclockt コンス トラクター |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockT::SyncLockT
dev_langs:
- C++
helpviewer_keywords:
- SyncLockT, constructor
ms.assetid: 713dfd9f-7369-4d86-b4a0-8b32c184d89b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c3353df1a73821a2009aeba2367f1892b06aba5b
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="synclocktsynclockt-constructor"></a>SyncLockT::SyncLockT コンストラクター
WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。  
  
## <a name="syntax"></a>構文  
  
```  
SyncLockT(  
   _Inout_ SyncLockT&& other  
);  
  
explicit SyncLockT(  
   typename SyncTraits::Type sync = SyncTraits::GetInvalidValue()  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `other`  
 右辺値参照を別の SyncLockT オブジェクト。  
  
 `sync`  
 SyncLockWithStatusT の別のオブジェクトへの参照。  
  
## <a name="remarks"></a>コメント  
 SyncLockT クラスの新しいインスタンスを初期化します。  
  
 最初のコンス トラクターの初期化パラメーターで指定された別の SyncLockT オブジェクトから現在の SyncLockT オブジェクト`other`、し、その他の SyncLockT オブジェクトを無効にします。 2 番目のコンス トラクターは`protected`、無効な状態を現在の SyncLockT オブジェクトを初期化します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers::Details  
  
## <a name="see-also"></a>関連項目  
 [SyncLockT クラス](../windows/synclockt-class.md)