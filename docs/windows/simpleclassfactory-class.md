---
title: SimpleClassFactory クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::SimpleClassFactory
dev_langs:
- C++
helpviewer_keywords:
- SimpleClassFactory class
ms.assetid: 6edda1b2-4e44-4e14-9364-72f519249962
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: debb78ba4be2731b8cffce1133518b0b4a04f63d
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33892762"
---
# <a name="simpleclassfactory-class"></a>SimpleClassFactory クラス
基底クラスを作成するための基本的なメカニズムを提供します。  
  
## <a name="syntax"></a>構文  
  
```  
template<typename Base>  
class SimpleClassFactory : public ClassFactory<>;  
```  
  
#### <a name="parameters"></a>パラメーター  
 `Base`  
 基本クラスです。  
  
## <a name="remarks"></a>コメント  
 基本クラスには、既定のコンス トラクターを提供する必要があります。  
  
 次のコード例で SimpleClassFactory を使用する方法を示します、 [ActivatableClassWithFactoryEx](../windows/activatableclass-macros.md)マクロです。  
  
 `ActivatableClassWithFactoryEx(MyClass, SimpleClassFactory, MyServerName);`  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[SimpleClassFactory::CreateInstance メソッド](../windows/simpleclassfactory-createinstance-method.md)|指定されたインターフェイスのインスタンスを作成します。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `I0`  
  
 `ChainInterfaces`  
  
 `I0`  
  
 `RuntimeClassBase`  
  
 `ImplementsHelper`  
  
 `DontUseNewUseMake`  
  
 `RuntimeClassFlags`  
  
 `RuntimeClassBaseT`  
  
 `RuntimeClass`  
  
 `ClassFactory`  
  
 `SimpleClassFactory`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** module.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>関連項目  
 [Microsoft::WRL 名前空間](../windows/microsoft-wrl-namespace.md)