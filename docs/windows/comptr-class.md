---
title: ComPtr クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::ComPtr
dev_langs:
- C++
helpviewer_keywords:
- ComPtr class
ms.assetid: a6551902-6819-478a-8df7-b6f312ab1fb0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 94146661b9a00b17732ce75f75bcc0194dcbddd4
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33882789"
---
# <a name="comptr-class"></a>ComPtr クラス
テンプレート パラメーターで指定されたインターフェイスを表す *スマート ポインター* 型を作成します。 ComPtr は、基になるインターフェイス ポインターの参照カウントを自動的に維持し、参照カウントがゼロになるとそのインターフェイスを解放します。  
  
## <a name="syntax"></a>構文  
  
```  
template <typename T>  
class ComPtr;  
  
template<class T>  
friend class ComPtr;  
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 ComPtr が表すインターフェイス。  
  
 `U`  
 現在の ComPtr がフレンドであるクラス (このパラメーターを使用するテンプレートは保護されています)。  
  
## <a name="remarks"></a>コメント  
 ComPtr <> は、基になるインターフェイス ポインターを表す型を宣言します。 ComPtr <> を使用して変数を宣言し、矢印のメンバー アクセス演算子を使用 (`->`) インターフェイスのメンバー関数にアクセスします。  
  
 スマート ポインターの詳細については、MSDN ライブラリの [COM Coding Practices](http://msdn.microsoft.com/en-us/76aca556-b4d6-4e67-a2a3-4439900f0c39)トピックで「COM スマート ポインター」のサブセクションを参照してください。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-typedefs"></a>パブリック typedef  
  
|名前|説明|  
|----------|-----------------|  
|`InterfaceType`|`T` テンプレート パラメーターで指定された型のシノニム。|  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[ComPtr::ComPtr コンストラクター](../windows/comptr-comptr-constructor.md)|ComPtr クラスの新しいインスタンスを初期化します。 オーバーロードは、既定、コピー、移動、および変換の各コンストラクターを提供します。|  
|[ComPtr::~ComPtr デストラクター](../windows/comptr-tilde-comptr-destructor.md)|ComPtr のインスタンスを初期化解除します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[ComPtr::As メソッド](../windows/comptr-as-method.md)|指定されたテンプレート パラメーターで識別されるインターフェイスを表す ComPtr オブジェクトを返します。|  
|[ComPtr::AsIID メソッド](../windows/comptr-asiid-method.md)|指定されたインターフェイス ID で識別されるインターフェイスを表す ComPtr オブジェクトを返します。|  
|[ComPtr::AsWeak メソッド](../windows/comptr-asweak-method.md)|現在のオブジェクトへの弱い参照を取得します。|  
|[ComPtr::Attach メソッド](../windows/comptr-attach-method.md)|この ComPtr と、現在のテンプレート型パラメーターで指定されたインターフェイスの種類を関連付けます。|  
|[ComPtr::CopyTo メソッド](../windows/comptr-copyto-method.md)|この ComPtr に関連付けられた現在のまたは指定されたインターフェイスを、指定された出力ポインターにコピーします。|  
|[ComPtr::Detach メソッド](../windows/comptr-detach-method.md)|この ComPtr が表すインターフェイスからその関連付けを解除します。|  
|[ComPtr::Get メソッド](../windows/comptr-get-method.md)|この ComPtr に関連付けられたインターフェイスへのポインターを取得します。|  
|[ComPtr::GetAddressOf メソッド](../windows/comptr-getaddressof-method.md)|[ptr_](../windows/comptr-ptr-data-member.md) データ メンバーのアドレスを取得します。これには、この ComPtr によって表されるインターフェイスへのポインターが含まれています。|  
|[ComPtr::ReleaseAndGetAddressOf メソッド](../windows/comptr-releaseandgetaddressof-method.md)|この ComPtr に関連付けられたインターフェイスを解放してから、 [ptr_](../windows/comptr-ptr-data-member.md) データ メンバーのアドレスを取得します。このアドレスには、解放されたインターフェイスへのポインターが含まれています。|  
|[ComPtr::Reset](../windows/comptr-reset.md)|この ComPtr に関連付けられているインターフェイスを指すポインターへのすべての参照を解放します。|  
|[ComPtr::Swap メソッド](../windows/comptr-swap-method.md)|指定された ComPtr によって管理されているインターフェイスと現在の ComPtr によって管理されるインターフェイスを交換します。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[ComPtr::InternalAddRef メソッド](../windows/comptr-internaladdref-method.md)|この ComPtr に関連付けられたインターフェイスの参照カウントをインクリメントします。|  
|[ComPtr::InternalRelease メソッド](../windows/comptr-internalrelease-method.md)|この ComPtr に関連付けられたインターフェイスに対して COM 解放操作を実行します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[ComPtr::operator Microsoft::WRL::Details::BoolType 演算子](../windows/comptr-operator-microsoft-wrl-details-booltype-operator.md)|ComPtr がインターフェイスのオブジェクト有効期間を管理しているかどうかを示します。|  
|[ComPtr::operator& 演算子](../windows/comptr-operator-ampersand-operator.md)|現在の ComPtr のアドレスを取得します。|  
|[ComPtr::operator= 演算子](../windows/comptr-operator-assign-operator.md)|値を現在の ComPtr に割り当てます。|  
|[ComPtr::operator-> 演算子](../windows/comptr-operator-arrow-operator.md)|現在のテンプレート パラメーターで指定された型へのポインターを取得します。|  
|[ComPtr::operator== 演算子](../windows/comptr-operator-equality-operator.md)|2 つの ComPtr オブジェクトが等しいかどうかを示します。|  
|[ComPtr::operator!= 演算子](../windows/comptr-operator-inequality-operator.md)|2 つの ComPtr オブジェクトが等しくないかどうかを示します。|  
  
### <a name="protected-data-members"></a>プロテクト データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[ComPtr::ptr_ データ メンバー](../windows/comptr-ptr-data-member.md)|この ComPtr に関連付けられ、管理されているインターフェイスへのポインターが含まれています。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `ComPtr`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** client.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>関連項目  
 [Microsoft::WRL 名前空間](../windows/microsoft-wrl-namespace.md)