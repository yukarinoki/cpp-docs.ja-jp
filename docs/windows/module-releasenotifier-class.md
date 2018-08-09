---
title: Module::releasenotifier クラス |Microsoft Docs
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
ms.openlocfilehash: 97c998f7e0814c5acae55dd3e9b747faed0242e1
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2018
ms.locfileid: "40016224"
---
# <a name="modulereleasenotifier-class"></a>Module::ReleaseNotifier クラス
モジュールの最後のオブジェクトがリリースされたときに、イベント ハンドラーを呼び出します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
class ReleaseNotifier;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[Module::ReleaseNotifier::~ReleaseNotifier デストラクター](../windows/module-releasenotifier-tilde-releasenotifier-destructor.md)|現在のインスタンスの初期化を解除、 **module::releasenotifier**クラス。|  
|[Module::ReleaseNotifier::ReleaseNotifier コンストラクター](../windows/module-releasenotifier-releasenotifier-constructor.md)|新しいインスタンスを初期化、 **module::releasenotifier**クラス。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[Module::ReleaseNotifier::Invoke メソッド](../windows/module-releasenotifier-invoke-method.md)|実装された場合、モジュールの最後のオブジェクトがリリースされたときに、イベント ハンドラーを呼び出します。|  
|[Module::ReleaseNotifier::Release](../windows/module-releasenotifier-release.md)|現在の削除**module::releasenotifier**オブジェクトのパラメーターを持つオブジェクトを構築したかどうかは**true**します。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `ReleaseNotifier`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** module.h  
  
 **名前空間:** Microsoft::WRL
 
 ## <a name="see-also"></a>関連項目
 [Module クラス](../windows/module-class.md)