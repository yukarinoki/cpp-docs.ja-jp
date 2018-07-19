---
title: WeakRef クラス |Microsoft ドキュメント
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
ms.openlocfilehash: ba7efc595be55b807cd3f044269db0debcb72407
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33891699"
---
# <a name="weakref-class"></a>WeakRef クラス
クラシック COM ではなく、Windows ランタイムでのみ使用できる *弱い参照* を表します。 弱い参照は、アクセスできる場合とできない場合があるオブジェクトを表します。  
  
## <a name="syntax"></a>構文  
  
```  
class WeakRef : public ComPtr<IWeakReference>  
```  
  
## <a name="remarks"></a>コメント  
 WeakRef オブジェクトは、 *強い参照*を保持します。これはオブジェクトと関連付けられ、有効な場合と無効な場合があります。 強い参照を取得するには、As() や AsIID() メソッドを呼び出します。 強い参照が有効な場合、関連付けられているオブジェクトにアクセスできます。 強い参照が無効な場合 (`nullptr`)、関連付けられているオブジェクトにアクセスできません。  
  
 WeakRef オブジェクトは通常、外部スレッドや外部アプリケーションによって存在が制御されるオブジェクトを表すために使用されます。 たとえば、ファイル オブジェクトへの参照から WeakRef オブジェクトを構築します。 ファイルが開いている間、強い参照は有効です。 しかし、ファイルが閉じられた場合、強い参照は無効になります。  
  
 なお、Windows 10 SDK では [As](../windows/weakref-as-method.md)、 [AsIID](../windows/weakref-asiid-method.md) 、 [CopyTo](../windows/weakref-copyto-method.md) の各メソッドの動作が変更されています。 以下のコードのように、以前は、これらのうちのいずれかのメソッドを呼び出した後、強い参照が正常に取得されたかどうかを判別するために `nullptr` の WeakRef を調べることができました。  
  
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
  
 上記のコードは、Windows 10 SDK (以降) の使用時には機能しません。 代わりに、確認用に渡されたポインター`nullptr`です。  
  
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
|[WeakRef::WeakRef コンストラクター](../windows/weakref-weakref-constructor.md)|WeakRef クラスの新しいインスタンスを初期化します。|  
|[WeakRef::~WeakRef デストラクター](../windows/weakref-tilde-weakref-destructor.md)|WeakRef クラスの現在のインスタンスの初期化を解除します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[WeakRef::As メソッド](../windows/weakref-as-method.md)|指定された ComPtr ポインター パラメーターを、指定されたインターフェイスを表すように設定します。|  
|[WeakRef::AsIID メソッド](../windows/weakref-asiid-method.md)|指定したインターフェイス ID を表すよう指定された ComPtr ポインター パラメーターを設定します。|  
|[WeakRef::CopyTo メソッド](../windows/weakref-copyto-method.md)|使用可能なインターフェイスへのポインターがあるなら、指定されたポインター変数にそれを割り当てます。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[WeakRef::operator& 演算子](../windows/weakref-operator-ampersand-operator.md)|現在の WeakRef オブジェクトを表す ComPtrRef オブジェクトを返します。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `ComPtr`  
  
 `WeakRef`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** client.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>関連項目  
 [Microsoft::WRL 名前空間](../windows/microsoft-wrl-namespace.md)