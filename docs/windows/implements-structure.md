---
title: 構造体を実装 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Implements
dev_langs:
- C++
helpviewer_keywords:
- Implements structure
ms.assetid: 29b13e90-34d4-4a0b-babd-5187c9eb0c36
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 1ecbf0b77feef7abeb67f8d0dc300da067d1f2da
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="implements-structure"></a>Implements 構造体
指定されたインターフェイスの QueryInterface と GetIid を実装します。  
  
## <a name="syntax"></a>構文  
  
```  
template <  
   typename I0,  
   typename I1 = Details::Nil,  
   typename I2 = Details::Nil,  
   typename I3 = Details::Nil,  
   typename I4 = Details::Nil,  
   typename I5 = Details::Nil,  
   typename I6 = Details::Nil,  
   typename I7 = Details::Nil,  
   typename I8 = Details::Nil,  
   typename I9 = Details::Nil  
>  
struct __declspec(novtable) Implements : Details::ImplementsHelper<RuntimeClassFlags<WinRt>, typename Details::InterfaceListHelper<I0, I1, I2, I3, I4, I5, I6, I7, I8, I9>::TypeT>, Details::ImplementsBase;  
template <  
   int flags,  
   typename I0,  
   typename I1,  
   typename I2,  
   typename I3,  
   typename I4,  
   typename I5,  
   typename I6,  
   typename I7,  
   typename I8  
>  
struct __declspec(novtable) Implements<RuntimeClassFlags<flags>, I0, I1, I2, I3, I4, I5, I6, I7, I8> : Details::ImplementsHelper<RuntimeClassFlags<flags>, typename Details::InterfaceListHelper<I0, I1, I2, I3, I4, I5, I6, I7, I8>::TypeT>, Details::ImplementsBase;  
```  
  
#### <a name="parameters"></a>パラメーター  
 `I0`  
 0 番目のインターフェイス ID です  (必須)。  
  
 `I1`  
 1 番目のインターフェイス ID です  (オプション)。  
  
 `I2`  
 2 番目のインターフェイス ID です  (オプション)。  
  
 `I3`  
 3 番目のインターフェイス ID です  (オプション)。  
  
 `I4`  
 4 番目のインターフェイス ID です  (オプション)。  
  
 `I5`  
 5 番目のインターフェイス ID です  (オプション)。  
  
 `I6`  
 6 番目のインターフェイス ID です  (オプション)。  
  
 `I7`  
 7 番目のインターフェイス ID です  (オプション)。  
  
 `I8`  
 8 番目のインターフェイス ID です  (オプション)。  
  
 `I9`  
 9 番目のインターフェイス ID です  (オプション)。  
  
 `flags`  
 クラスの構成フラグです。 1 つまたは複数[RuntimeClassType](../windows/runtimeclasstype-enumeration.md)列挙体で指定されている、 [RuntimeClassFlags](../windows/runtimeclassflags-structure.md)構造体。  
  
## <a name="remarks"></a>コメント  
 指定したインターフェイスのリストから派生し、QueryInterface と GetIid をヘルパー テンプレートを実装します。  
  
 各`I0`を通じて`I9`インターフェイス パラメーターが IInspectable のいずれかの IUnknown から派生する必要がありますまたは[ChainInterfaces](../windows/chaininterfaces-structure.md)テンプレート。 `flags`パラメーターは、サポートが IUnknown または IInspectable に対して生成されたかどうかを決定します。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-typedefs"></a>パブリック typedef  
  
|名前|説明|  
|----------|-----------------|  
|`ClassFlags`|`RuntimeClassFlags<WinRt>` と同義。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[Implements::CanCastTo メソッド](../windows/implements-cancastto-method.md)|指定されたインターフェイスへのポインターを取得します。|  
|[Implements::CastToUnknown メソッド](../windows/implements-casttounknown-method.md)|基になる IUnknown インターフェイスへのポインターを取得します。|  
|[Implements::FillArrayWithIid メソッド](../windows/implements-fillarraywithiid-method.md)|指定した配列の要素に現在の 0 番目のテンプレート パラメーターで指定されたインターフェイス ID を挿入します。|  
  
### <a name="protected-constants"></a>プロテクト コンス トラクター  
  
|名前|説明|  
|----------|-----------------|  
|[Implements::IidCount 定数](../windows/implements-iidcount-constant.md)|実装されたインターフェイス Id の数を保持します。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `I0`  
  
 `ChainInterfaces`  
  
 `I0`  
  
 `ImplementsBase`  
  
 `ImplementsHelper`  
  
 `Implements`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** implements.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>関連項目  
 [Microsoft::WRL 名前空間](../windows/microsoft-wrl-namespace.md)