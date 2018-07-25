---
title: Module::methodreleasenotifier クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::MethodReleaseNotifier
dev_langs:
- C++
helpviewer_keywords:
- MethodReleaseNotifier class
ms.assetid: 5c2902be-964b-488f-9f1c-adf504995cbc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 217e58f73130922d45f0d303e1e91858e8c2272f
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33880828"
---
# <a name="modulemethodreleasenotifier-class"></a>Module::MethodReleaseNotifier クラス
現在のモジュールの最後のオブジェクトを解放すると、イベント ハンドラーを呼び出します。 イベント ハンドラーは、オブジェクトとそのメソッドへのポインターのメンバーによって指定されます。  
  
## <a name="syntax"></a>構文  
  
```  
template<typename T>  
class MethodReleaseNotifier : public ReleaseNotifier;  
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 メンバー関数がある、イベント ハンドラー オブジェクトの型。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[Module::MethodReleaseNotifier::MethodReleaseNotifier コンストラクター](../windows/module-methodreleasenotifier-methodreleasenotifier-constructor.md)|Module::methodreleasenotifier クラスの新しいインスタンスを初期化します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[Module::MethodReleaseNotifier::Invoke メソッド](../windows/module-methodreleasenotifier-invoke-method.md)|Module::methodreleasenotifier の現在のオブジェクトに関連付けられているイベント ハンドラーを呼び出します。|  
  
### <a name="protected-data-members"></a>プロテクト データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[Module::MethodReleaseNotifier::method_ データ メンバー](../windows/module-methodreleasenotifier-method-data-member.md)|Module::methodreleasenotifier、現在のイベント ハンドラーへのポインターを保持します。|  
|[Module::MethodReleaseNotifier::object_ データ メンバー](../windows/module-methodreleasenotifier-object-data-member.md)|メンバー関数がある現在の module::methodreleasenotifier オブジェクトのイベント ハンドラー オブジェクトへのポインターを保持します。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `ReleaseNotifier`  
  
 `MethodReleaseNotifier`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** module.h  
  
 **名前空間:** Microsoft::WRL
 
 ## <a name="see-also"></a>関連項目
 [Module クラス](../windows/module-class.md)