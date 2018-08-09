---
title: ComPtr クラス |Microsoft Docs
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
ms.openlocfilehash: 7e4866df2d948d02a53b2532b0832f161d07ff8c
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/08/2018
ms.locfileid: "39647561"
---
# <a name="comptr-class"></a>ComPtr クラス
テンプレート パラメーターで指定されたインターフェイスを表す *スマート ポインター* 型を作成します。 **ComPtr**自動的に基になるインターフェイス ポインターの参照カウントを維持し、参照カウントが 0 になるインターフェイスを解放します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
template <typename T>  
class ComPtr;  
  
template<class T>  
friend class ComPtr;  
```  
  
### <a name="parameters"></a>パラメーター  
 *T*  
 インターフェイスを**ComPtr**を表します。  
  
 *U*  
 クラスを現在**ComPtr**フレンドです。 (このパラメーターを使用するテンプレートは保護されています)。  
  
## <a name="remarks"></a>Remarks  
 `ComPtr<>` 基になるインターフェイス ポインターを表す型を宣言します。 使用して、`ComPtr<>`変数を宣言し、矢印のメンバー アクセス演算子を使用 (`->`) インターフェイスのメンバー関数にアクセスします。  
  
 スマート ポインターの詳細については、の「COM スマート ポインター」サブセクションを参照してください、 [COM Coding Practices](http://msdn.microsoft.com/76aca556-b4d6-4e67-a2a3-4439900f0c39)MSDN ライブラリの「します。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-typedefs"></a>パブリック typedef  
  
|名前|説明|  
|----------|-----------------|  
|`InterfaceType`|指定された型のシノニム、 *T*テンプレート パラメーター。|  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[ComPtr::ComPtr コンストラクター](../windows/comptr-comptr-constructor.md)|新しいインスタンスを初期化します、 **ComPtr**クラス。 オーバーロードは、既定、コピー、移動、および変換の各コンストラクターを提供します。|  
|[ComPtr::~ComPtr デストラクター](../windows/comptr-tilde-comptr-destructor.md)|インスタンスを初期化解除**ComPtr**します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[ComPtr::As メソッド](../windows/comptr-as-method.md)|返します、 **ComPtr**指定されたテンプレート パラメーターで識別されるインターフェイスを表すオブジェクト。|  
|[ComPtr::AsIID メソッド](../windows/comptr-asiid-method.md)|返します、 **ComPtr**指定したインターフェイス ID で識別されるインターフェイスを表すオブジェクトを|  
|[ComPtr::AsWeak メソッド](../windows/comptr-asweak-method.md)|現在のオブジェクトへの弱い参照を取得します。|  
|[ComPtr::Attach メソッド](../windows/comptr-attach-method.md)|これを関連付けます**ComPtr**現在のテンプレート型パラメーターで指定したインターフェイス型にします。|  
|[ComPtr::CopyTo メソッド](../windows/comptr-copyto-method.md)|これに関連付けられている現在または指定されたインターフェイスのコピー **ComPtr**への指定された出力ポインター。|  
|[ComPtr::Detach メソッド](../windows/comptr-detach-method.md)|この関連付けを解除**ComPtr**それが表すインターフェイスから。|  
|[ComPtr::Get メソッド](../windows/comptr-get-method.md)|これに関連付けられているインターフェイスへのポインターを取得します。 **ComPtr**します。|  
|[ComPtr::GetAddressOf メソッド](../windows/comptr-getaddressof-method.md)|アドレスを取得、 [ptr _](../windows/comptr-ptr-data-member.md)データ メンバーは、これによって表されるインターフェイスへのポインターを含む**ComPtr**します。|  
|[ComPtr::ReleaseAndGetAddressOf メソッド](../windows/comptr-releaseandgetaddressof-method.md)|これに関連付けられているインターフェイスを解放**ComPtr**しのアドレスを取得し、 [ptr _](../windows/comptr-ptr-data-member.md)データ メンバーは、リリースされたインターフェイスへのポインターが含まれています。|  
|[ComPtr::Reset](../windows/comptr-reset.md)|これに関連付けられているインターフェイス ポインターのすべての参照を解放**ComPtr**します。|  
|[ComPtr::Swap メソッド](../windows/comptr-swap-method.md)|現在の管理インターフェイスを交換**ComPtr** 、指定した管理インターフェイスで**ComPtr**します。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[ComPtr::InternalAddRef メソッド](../windows/comptr-internaladdref-method.md)|これに関連付けられているインターフェイスの参照カウントをインクリメント**ComPtr**します。|  
|[ComPtr::InternalRelease メソッド](../windows/comptr-internalrelease-method.md)|これに関連付けられているインターフェイスで COM 解放操作を行います**ComPtr**します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[ComPtr::operator Microsoft::WRL::Details::BoolType 演算子](../windows/comptr-operator-microsoft-wrl-details-booltype-operator.md)|示すかどうかを**ComPtr**インターフェイスのオブジェクトの有効期間を管理します。|  
|[ComPtr::operator& 演算子](../windows/comptr-operator-ampersand-operator.md)|現在のアドレスを取得**ComPtr**します。|  
|[ComPtr::operator= 演算子](../windows/comptr-operator-assign-operator.md)|現在の値を代入**ComPtr**します。|  
|[ComPtr::operator-> 演算子](../windows/comptr-operator-arrow-operator.md)|現在のテンプレート パラメーターで指定された型へのポインターを取得します。|  
|[ComPtr::operator== 演算子](../windows/comptr-operator-equality-operator.md)|示す 2 つかどうか**ComPtr**オブジェクトが等しい。|  
|[ComPtr::operator!= 演算子](../windows/comptr-operator-inequality-operator.md)|示す 2 つかどうか**ComPtr**オブジェクトが等しくないです。|  
  
### <a name="protected-data-members"></a>プロテクト データ メンバー  
  
|name|説明|  
|----------|-----------------|  
|[ComPtr::ptr_ データ メンバー](../windows/comptr-ptr-data-member.md)|使用すると、関連付けられているされ、これによって管理されるインターフェイスへのポインターを含む**ComPtr**します。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `ComPtr`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** client.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>関連項目  
 [Microsoft::WRL 名前空間](../windows/microsoft-wrl-namespace.md)