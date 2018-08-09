---
title: Module::GenericReleaseNotifier::GenericReleaseNotifier コンス トラクター |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::GenericReleaseNotifier::GenericReleaseNotifier
dev_langs:
- C++
helpviewer_keywords:
- GenericReleaseNotifier, constructor
ms.assetid: feb5b687-a4b0-4809-9022-8f292181b7a1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5aa78562c934c41b2ff2ab7b381f6b2612426651
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2018
ms.locfileid: "40014589"
---
# <a name="modulegenericreleasenotifiergenericreleasenotifier-constructor"></a>Module::GenericReleaseNotifier::GenericReleaseNotifier コンストラクター
新しいインスタンスを初期化、 **module::genericreleasenotifier**クラス。  
  
## <a name="syntax"></a>構文  
  
```cpp  
GenericReleaseNotifier(  
   T callback,   
   bool release  
) throw() : ReleaseNotifier(release), callback_(callback);  
```  
  
### <a name="parameters"></a>パラメーター  
 *コールバック*  
 ラムダをファンクター、またはかっこ関数の演算子を呼び出すことができる関数へのポインター イベント ハンドラー (`()`)。  
  
 *release*  
 指定**true** 、基になる呼び出しを有効にする[モジュール:: ReleaseNotifier::Release()](../windows/module-releasenotifier-release.md)メソッド。 それ以外の場合、指定**false**します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** module.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>関連項目  
 [Module::GenericReleaseNotifier クラス](../windows/module-genericreleasenotifier-class.md)