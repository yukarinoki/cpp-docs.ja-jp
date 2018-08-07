---
title: 構造体の実装 |Microsoft Docs
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
ms.openlocfilehash: 0dc23a9c90fc2112d67180ceae86ebde0e057b06
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2018
ms.locfileid: "39607807"
---
# <a name="implements-structure"></a>Implements 構造体
実装`QueryInterface`と`GetIid`のインターフェイスで指定します。  
  
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
  
### <a name="parameters"></a>パラメーター  
 *I0*  
 0 番目のインターフェイス ID です  (必須)。  
  
 *I1*  
 1 番目のインターフェイス ID です  (オプション)。  
  
 *I2*  
 2 番目のインターフェイス ID です  (オプション)。  
  
 *I3*  
 3 番目のインターフェイス ID です  (オプション)。  
  
 *I4*  
 4 番目のインターフェイス ID です  (オプション)。  
  
 *I5*  
 5 番目のインターフェイス ID です  (オプション)。  
  
 *I6*  
 6 番目のインターフェイス ID です  (オプション)。  
  
 *I7*  
 7 番目のインターフェイス ID です  (オプション)。  
  
 *I8*  
 8 番目のインターフェイス ID です  (オプション)。  
  
 *I9*  
 9 番目のインターフェイス ID です  (オプション)。  
  
 *flags*  
 クラスの構成フラグです。 1 つまたは複数[RuntimeClassType](../windows/runtimeclasstype-enumeration.md)列挙体で指定されている、 [RuntimeClassFlags](../windows/runtimeclassflags-structure.md)構造体。  
  
## <a name="remarks"></a>Remarks  
 指定したインターフェイスの一覧から派生し、実装のヘルパー テンプレート`QueryInterface`と`GetIid`します。  
  
 各*I0*を通じて*I9*インターフェイス パラメーターは、いずれかから派生する必要があります`IUnknown`、 `IInspectable`、または[ChainInterfaces](../windows/chaininterfaces-structure.md)テンプレート。 *フラグ*のサポートが生成されるかどうかを判別します`IUnknown`または`IInspectable`します。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-typedefs"></a>パブリック typedef  
  
|名前|説明|  
|----------|-----------------|  
|`ClassFlags`|`RuntimeClassFlags<WinRt>` と同義。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[Implements::CanCastTo メソッド](../windows/implements-cancastto-method.md)|指定したインターフェイスへのポインターを取得します。|  
|[Implements::CastToUnknown メソッド](../windows/implements-casttounknown-method.md)|基になるポインターを取得します。`IUnknown`インターフェイス。|  
|[Implements::FillArrayWithIid メソッド](../windows/implements-fillarraywithiid-method.md)|指定した配列の要素に現在の 0 番目のテンプレート パラメーターで指定されたインターフェイス ID を挿入します。|  
  
### <a name="protected-constants"></a>保護されている定数  
  
|name|説明|  
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