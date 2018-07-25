---
title: Module::releasenotifier クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::ReleaseNotifier
dev_langs:
- C++
helpviewer_keywords:
- ReleaseNotifier class
ms.assetid: 17249cd1-4d88-42e3-8146-da9e942d12bd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 76edb403fae12dd8b6221d8bd6ec82424bc5a4f7
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33878393"
---
# <a name="modulereleasenotifier-class"></a>Module::ReleaseNotifier クラス
モジュール内の最後のオブジェクトを解放すると、イベント ハンドラーを呼び出します。  
  
## <a name="syntax"></a>構文  
  
```  
class ReleaseNotifier;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[Module::ReleaseNotifier::~ReleaseNotifier デストラクター](../windows/module-releasenotifier-tilde-releasenotifier-destructor.md)|Module::releasenotifier クラスの現在のインスタンスの初期化を解除します。|  
|[Module::ReleaseNotifier::ReleaseNotifier コンストラクター](../windows/module-releasenotifier-releasenotifier-constructor.md)|Module::releasenotifier クラスの新しいインスタンスを初期化します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[Module::ReleaseNotifier::Invoke メソッド](../windows/module-releasenotifier-invoke-method.md)|実装された場合、モジュール内の最後のオブジェクトが離されると、イベント ハンドラーを呼び出します。|  
|[Module::ReleaseNotifier::Release](../windows/module-releasenotifier-release.md)|パラメーターを持つオブジェクトを構築した場合は、現在の module::releasenotifier オブジェクトを削除`true`です。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `ReleaseNotifier`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** module.h  
  
 **名前空間:** Microsoft::WRL
 
 ## <a name="see-also"></a>関連項目
 [Module クラス](../windows/module-class.md)