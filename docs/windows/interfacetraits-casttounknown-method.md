---
title: Interfacetraits::casttounknown メソッド |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::InterfaceTraits::CastToUnknown
dev_langs:
- C++
helpviewer_keywords:
- CastToUnknown method
ms.assetid: aca47fa0-3c60-47f2-a73c-258f7160adff
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: bdb87fe43b5cc6a5d2c141ac534e3b5e781f91e8
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2018
ms.locfileid: "40019918"
---
# <a name="interfacetraitscasttounknown-method"></a>InterfaceTraits::CastToUnknown メソッド
WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。  
  
## <a name="syntax"></a>構文  
  
```cpp  
template<typename T>  
static __forceinline IUnknown* CastToUnknown(  
   _In_ T* ptr  
);  
```  
  
### <a name="parameters"></a>パラメーター  
 *T*  
 パラメーターの型*ptr*します。  
  
 *ptr*  
 型へのポインター *T*します。  
  
## <a name="return-value"></a>戻り値  
 これから、IUnknown へのポインター`Base`が派生します。  
  
## <a name="remarks"></a>Remarks  
 指定したポインターへのポインターにキャスト`IUnknown`します。  
  
 詳細については`Base`、パブリック Typedef」セクションを参照してください。 [InterfaceTraits 構造体](../windows/interfacetraits-structure.md)します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** implements.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>関連項目  
 [InterfaceTraits 構造体](../windows/interfacetraits-structure.md)   
 [Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)