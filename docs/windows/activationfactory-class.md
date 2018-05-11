---
title: ActivationFactory クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::ActivationFactory
dev_langs:
- C++
helpviewer_keywords:
- ActivationFactory class
ms.assetid: 5faddf1f-43b6-4f8a-97de-8c9d3ae1e1ff
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6775e9466ed337a070b6a234a4d65bb949a009e4
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="activationfactory-class"></a>ActivationFactory クラス
1 つ以上のクラスを Windows ランタイムによってアクティブ化できるようにします。  
  
## <a name="syntax"></a>構文  
  
```  
template <  
   typename I0 = Details::Nil,  
   typename I1 = Details::Nil,  
   typename I2 = Details::Nil  
>  
class ActivationFactory : public Details::RuntimeClass<typename Details::InterfaceListHelper<IActivationFactory, I0, I1, I2, Details::Nil>::TypeT, RuntimeClassFlags<WinRt | InhibitWeakReference>, false>;  
```  
  
#### <a name="parameters"></a>パラメーター  
 `I0`  
 0 番目のインターフェイスです。  
  
 `I1`  
 最初のインターフェイスです。  
  
 `I2`  
 2 番目のインターフェイスです。  
  
## <a name="remarks"></a>コメント  
 ActivationFactory は、登録メソッドと IActivationFactory インターフェイスの基本的な機能を提供します。 ActivationFactory では、カスタム ファクトリの実装を提供することもできます。  
  
 次のコード フラグメントでは、シンボリック ActivationFactory を使用する方法を示しています。  
  
 [!code-cpp[wrl-microsoft__wrl__activationfactory#1](../windows/codesnippet/CPP/activationfactory-class_1.cpp)]  
  
 次のコード フラグメントは、使用する方法を示します、 [Implements](../windows/implements-structure.md)構造を 3 つ以上のインターフェイス Id を指定します。  
  
 `struct MyFactory : ActivationFactory<Implements<I1, I2, I3>, I4, I5>;`  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[ActivationFactory::ActivationFactory コンストラクター](../windows/activationfactory-activationfactory-constructor.md)|ActivationFactory クラスを初期化します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[ActivationFactory::AddRef メソッド](../windows/activationfactory-addref-method.md)|ActivationFactory、現在の参照カウントをインクリメントします。|  
|[ActivationFactory::GetIids メソッド](../windows/activationfactory-getiids-method.md)|実装されたインターフェイス Id の配列を取得します。|  
|[ActivationFactory::GetRuntimeClassName メソッド](../windows/activationfactory-getruntimeclassname-method.md)|現在の ActivationFactory をインスタンス化するオブジェクトのランタイム クラス名を取得します。|  
|[ActivationFactory::GetTrustLevel メソッド](../windows/activationfactory-gettrustlevel-method.md)|現在の ActivationFactory がインスタンス化するオブジェクトの信頼レベルを取得します。|  
|[ActivationFactory::QueryInterface メソッド](../windows/activationfactory-queryinterface-method.md)|指定されたインターフェイスへのポインターを取得します。|  
|[ActivationFactory::Release メソッド](../windows/activationfactory-release-method.md)|ActivationFactory の現在のオブジェクトの参照カウントをデクリメントします。|  
  
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
  
 `ActivationFactory`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** module.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>関連項目  
 [Microsoft::WRL 名前空間](../windows/microsoft-wrl-namespace.md)