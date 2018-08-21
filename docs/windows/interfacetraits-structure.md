---
title: InterfaceTraits 構造体 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::InterfaceTraits
dev_langs:
- C++
helpviewer_keywords:
- InterfaceTraits structure
ms.assetid: ede0c284-19a7-4892-9738-ff3da4923d0a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6cb96b90a069c12e65c53158717d9a89fb0aed3d
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2018
ms.locfileid: "40014101"
---
# <a name="interfacetraits-structure"></a>InterfaceTraits 構造体
WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。  
  
## <a name="syntax"></a>構文  
  
```cpp  
template<  
   typename I0  
>  
struct __declspec(novtable) InterfaceTraits;  
template<typename CloakedType>  
struct __declspec(novtable) InterfaceTraits<CloakedIid<CloakedType>>;  
  
template<>  
struct __declspec(novtable) InterfaceTraits<Nil>;  
```  
  
### <a name="parameters"></a>パラメーター  
 *I0*  
 インターフェイスの名前。  
  
 *CloakedType*  
 `RuntimeClass`、`Implements`と`ChainInterfaces`、ことができなくなるの一覧で、インターフェイスのインターフェイス Id をサポートします。  
  
## <a name="remarks"></a>Remarks  
 インターフェイスの一般的な特性を実装します。  
  
 2 番目のテンプレートは、クロークされたインターフェイスの特殊化です。 3 番目のテンプレートは、パラメーターが Nil の特殊化です。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-typedefs"></a>パブリック typedef  
  
|名前|説明|  
|----------|-----------------|  
|`Base`|シノニム、 *I0*テンプレート パラメーター。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[InterfaceTraits::CanCastTo メソッド](../windows/interfacetraits-cancastto-method.md)|指定したポインターへのポインターにキャストできるかどうかを示す`Base`します。|  
|[InterfaceTraits::CastToBase メソッド](../windows/interfacetraits-casttobase-method.md)|指定したポインターへのポインターにキャスト`Base`します。|  
|[InterfaceTraits::CastToUnknown メソッド](../windows/interfacetraits-casttounknown-method.md)|指定したポインターへのポインターにキャスト`IUnknown`します。|  
|[InterfaceTraits::FillArrayWithIid メソッド](../windows/interfacetraits-fillarraywithiid-method.md)|インターフェイス ID を割り当てます`Base`インデックス引数で指定された配列の要素にします。|  
|[InterfaceTraits::Verify メソッド](../windows/interfacetraits-verify-method.md)|検証が行われます`Base`は正しく派生します。|  
  
### <a name="public-constants"></a>パブリック定数  
  
|name|説明|  
|----------|-----------------|  
|[InterfaceTraits::IidCount 定数](../windows/interfacetraits-iidcount-constant.md)|インターフェイスに関連付けられた現在の Id の数を保持する**InterfaceTraits**オブジェクト。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `InterfaceTraits`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** implements.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>関連項目  
 [Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)