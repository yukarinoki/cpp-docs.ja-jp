---
title: Module::MethodReleaseNotifier::MethodReleaseNotifier コンス トラクター |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::MethodReleaseNotifier::MethodReleaseNotifier
dev_langs:
- C++
helpviewer_keywords:
- MethodReleaseNotifier, constructor
ms.assetid: 762e2ca4-0a92-49de-9ff5-d3efa0f067c0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 01c000ee928e9394827a69acb48ef0f41478a699
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2018
ms.locfileid: "40018508"
---
# <a name="modulemethodreleasenotifiermethodreleasenotifier-constructor"></a>Module::MethodReleaseNotifier::MethodReleaseNotifier コンストラクター
新しいインスタンスを初期化、 **module::methodreleasenotifier**クラス。  
  
## <a name="syntax"></a>構文  
  
```cpp  
MethodReleaseNotifier(  
   _In_ T* object,   
   _In_ void (T::* method)(),   
   bool release) throw() :  
            ReleaseNotifier(release), object_(object),   
            method_(method);  
```  
  
### <a name="parameters"></a>パラメーター  
 *object*  
 メンバー関数は、イベント ハンドラー オブジェクト。  
  
 *method*  
 パラメーターのメンバー関数は、*オブジェクト*イベント ハンドラーは。  
  
 *release*  
 指定**true** 、基になる呼び出しを有効にする[モジュール:: ReleaseNotifier::Release()](../windows/module-releasenotifier-release.md)メソッド。 それ以外の場合、指定**false**します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** module.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>関連項目  
 [Module::MethodReleaseNotifier クラス](../windows/module-methodreleasenotifier-class.md)