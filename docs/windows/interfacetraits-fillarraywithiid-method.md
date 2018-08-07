---
title: Interfacetraits::fillarraywithiid メソッド |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::InterfaceTraits::FillArrayWithIid
dev_langs:
- C++
helpviewer_keywords:
- FillArrayWithIid method
ms.assetid: 73583177-adc9-4fcb-917d-fa7e6d07c990
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 1ef552e5025a18eb4c778f9d08389d2b7e3634d5
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2018
ms.locfileid: "39605657"
---
# <a name="interfacetraitsfillarraywithiid-method"></a>InterfaceTraits::FillArrayWithIid メソッド
WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。  
  
## <a name="syntax"></a>構文  
  
```  
__forceinline static void FillArrayWithIid(  
   _Inout_ unsigned long &index,  
   _In_ IID* iids  
);  
```  
  
### <a name="parameters"></a>パラメーター  
 *index*  
 0 から始まるインデックス値を含むフィールドへのポインター。  
  
 *iid*  
 インターフェイスの Id の配列。  
  
## <a name="remarks"></a>Remarks  
 インターフェイス ID を割り当てます`Base`インデックス引数で指定された配列の要素にします。  
  
 、この API の名前とは対照的に 1 つだけの配列の要素が変更された;全体の配列ではありません。  
  
 詳細については`Base`、パブリック Typedef」セクションを参照してください。 [InterfaceTraits 構造体](../windows/interfacetraits-structure.md)します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** implements.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>関連項目  
 [InterfaceTraits 構造体](../windows/interfacetraits-structure.md)   
 [Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)