---
title: SafeGreaterThanEquals |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- SafeGreaterThanEquals
dev_langs:
- C++
helpviewer_keywords:
- SafeGreaterThanEquals function
ms.assetid: 43312fa9-d925-4f9f-a352-a190c02b3005
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a33fd059b90248a53d355f09f074c9b52bd93ccf
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2018
ms.locfileid: "39606557"
---
# <a name="safegreaterthanequals"></a>SafeGreaterThanEquals
2 つの数値を比較します。  
  
## <a name="syntax"></a>構文  
  
```  
template <typename T, typename U>  
inline bool SafeGreaterThanEquals (  
   const T t,  
   const U u  
) throw ();  
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*t*  
 比較する最初の数値。 これは、型でなければなりません`T`します。  
  
 [in]*u*  
 比較する 2 番目の数値。 これは、型でなければなりません`U`します。  
  
## <a name="return-value"></a>戻り値  
 **true**場合*t*がより大きいまたは等しい*u*。 そうしないと**false**します。  
  
## <a name="remarks"></a>Remarks  
 **SafeGreaterThanEquals** 2 つの異なる型の数値を比較することができますので、標準的な比較演算子が向上します。  
  
 このメソッドの一部は、 [SafeInt ライブラリ](../windows/safeint-library.md)のインスタンスを作成せず、単一の比較操作のものでは、 [SafeInt クラス](../windows/safeint-class.md)します。  
  
> [!NOTE]
>  このメソッドは、単一の数値演算を保護する必要がありますにのみ使用する必要があります。 使用する必要があります複数の操作がある場合、`SafeInt`個々 のスタンドアロン関数の呼び出しではなくクラス。  
  
 テンプレートの種類の詳細については`T`と`U`を参照してください[SafeInt 関数](../windows/safeint-functions.md)します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** safeint.h  
  
 **Namespace:** Microsoft::Utilities  
  
## <a name="see-also"></a>関連項目  
 [SafeInt 関数](../windows/safeint-functions.md)   
 [SafeInt ライブラリ](../windows/safeint-library.md)   
 [SafeInt クラス](../windows/safeint-class.md)   
 [SafeGreaterThan](../windows/safegreaterthan.md)   
 [SafeLessThanEquals](../windows/safelessthanequals.md)   
 [SafeLessThan](../windows/safelessthan.md)