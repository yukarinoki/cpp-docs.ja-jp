---
title: ActivationFactory クラス |Microsoft Docs
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
ms.openlocfilehash: 18ce213d6c4bedd0bcaa2be1af33281ae69f6ad1
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/02/2018
ms.locfileid: "39461506"
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
 *I0*  
 0 番目のインターフェイスです。  
  
 *I1*  
 最初のインターフェイス。  
  
 *I2*  
 2 番目のインターフェイス。  
  
## <a name="remarks"></a>Remarks  
 **ActivationFactory**登録メソッドとの基本的な機能を提供します、`IActivationFactory`インターフェイス。 **ActivationFactory**カスタム ファクトリの実装を提供することもできます。  
  
 次のコード フラグメントでは、シンボリック ActivationFactory を使用する方法を示しています。  
  
 [!code-cpp[wrl-microsoft__wrl__activationfactory#1](../windows/codesnippet/CPP/activationfactory-class_1.cpp)]  
  
 次のコード フラグメントは、使用する方法を示します、[実装](../windows/implements-structure.md)3 つ以上のインターフェイス Id を指定する構造体。  
  
 `struct MyFactory : ActivationFactory<Implements<I1, I2, I3>, I4, I5>;`  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[ActivationFactory::ActivationFactory コンストラクター](../windows/activationfactory-activationfactory-constructor.md)|初期化します、 **ActivationFactory**クラス。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[ActivationFactory::AddRef メソッド](../windows/activationfactory-addref-method.md)|現在の参照カウントをインクリメント**ActivationFactory**オブジェクト。|  
|[ActivationFactory::GetIids メソッド](../windows/activationfactory-getiids-method.md)|実装されたインターフェイス Id の配列を取得します。|  
|[ActivationFactory::GetRuntimeClassName メソッド](../windows/activationfactory-getruntimeclassname-method.md)|オブジェクトのランタイム クラス名を取得、現在**ActivationFactory**をインスタンス化します。|  
|[ActivationFactory::GetTrustLevel メソッド](../windows/activationfactory-gettrustlevel-method.md)|現在の ActivationFactory がインスタンス化するオブジェクトの信頼レベルを取得します。|  
|[ActivationFactory::QueryInterface メソッド](../windows/activationfactory-queryinterface-method.md)|指定したインターフェイスへのポインターを取得します。|  
|[ActivationFactory::Release メソッド](../windows/activationfactory-release-method.md)|現在の参照カウントをデクリメント**ActivationFactory**オブジェクト。|  
  
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