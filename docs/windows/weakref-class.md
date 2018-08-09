---
title: WeakRef クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::WeakRef
dev_langs:
- C++
helpviewer_keywords:
- WeakRef class
ms.assetid: 572be703-c641-496c-8af5-ad6164670ba1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f56b35ffb53da8947982359174784a0dbb3cef85
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2018
ms.locfileid: "40012587"
---
# <a name="weakref-class"></a>WeakRef クラス
クラシック COM ではなく、Windows ランタイムでのみ使用できる *弱い参照* を表します。 弱い参照は、アクセスできる場合とできない場合があるオブジェクトを表します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
class WeakRef : public ComPtr<IWeakReference>  
```  
  
## <a name="remarks"></a>Remarks  
 A **WeakRef**オブジェクトを保持する*強い参照*、これは、オブジェクトに関連付けられ、有効または無効にすることができます。 呼び出す、`As()`または`AsIID()`強い参照を取得します。 強い参照が有効な場合、関連付けられているオブジェクトにアクセスできます。 強い参照が有効な場合 (**nullptr**)、関連付けられているオブジェクトにアクセスできません。  
  
 A **WeakRef**オブジェクトは通常、外部スレッドまたはアプリケーションによって存在が制御されるオブジェクトを表すために使用します。 たとえば、構築、 **WeakRef**ファイル オブジェクトへの参照からオブジェクト。 ファイルが開いている間、強い参照は有効です。 しかし、ファイルが閉じられた場合、強い参照は無効になります。  
  
 なお、Windows 10 SDK では [As](../windows/weakref-as-method.md)、 [AsIID](../windows/weakref-asiid-method.md) 、 [CopyTo](../windows/weakref-copyto-method.md) の各メソッドの動作が変更されています。 以前は、これらのメソッドを呼び出すことでしたの WeakRef を調べる**nullptr**が次のコードのように、強い参照を取得が正常にかどうかを決定します。  
  
```cpp  
WeakRef wr;  
strongComptrRef.AsWeak(&wr);  
  
// Now suppose that the object strongComPtrRef points to no longer exists  
// and the following code tries to get a strong ref from the weak ref:  
ComPtr<ISomeInterface> strongRef;  
HRESULT hr = wr.As(&strongRef);  
  
// This check won't work with the Windows 10 SDK version of the library.  
// Check the input pointer instead.  
if(wr == nullptr)  
{  
    wprintf(L"Couldn’t get strong ref!");  
}  
```  
  
 上記のコードは、Windows 10 SDK (以降) の使用時には機能しません。 渡されたポインターを代わりに、チェック**nullptr**します。  
  
```cpp  
if (strongRef == nullptr)  
{  
    wprintf(L"Couldn't get strong ref!");  
}  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[WeakRef::WeakRef コンストラクター](../windows/weakref-weakref-constructor.md)|新しいインスタンスを初期化、 **WeakRef**クラス。|  
|[WeakRef::~WeakRef デストラクター](../windows/weakref-tilde-weakref-destructor.md)|現在のインスタンスの初期化を解除、 **WeakRef**クラス。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[WeakRef::As メソッド](../windows/weakref-as-method.md)|指定した設定`ComPtr`ポインター パラメーターを指定したインターフェイスを表します。|  
|[WeakRef::AsIID メソッド](../windows/weakref-asiid-method.md)|指定した設定`ComPtr`ポインター パラメーターを指定したインターフェイス ID を表す|  
|[WeakRef::CopyTo メソッド](../windows/weakref-copyto-method.md)|使用可能なインターフェイスへのポインターがあるなら、指定されたポインター変数にそれを割り当てます。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[WeakRef::operator& 演算子](../windows/weakref-operator-ampersand-operator.md)|返します、`ComPtrRef`現在を表すオブジェクトを**WeakRef**オブジェクト。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `ComPtr`  
  
 `WeakRef`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** client.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>関連項目  
 [Microsoft::WRL 名前空間](../windows/microsoft-wrl-namespace.md)