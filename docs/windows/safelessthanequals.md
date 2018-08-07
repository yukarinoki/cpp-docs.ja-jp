---
title: SafeLessThanEquals |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- SafeLessThanEquals
dev_langs:
- C++
helpviewer_keywords:
- SafeLessThanEquals function
ms.assetid: cbd70526-faf2-4fbc-96a0-b61e8cf5f04a
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e6e1dc50333839764ce37e9d6d09e106e1ae0c2d
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2018
ms.locfileid: "39604578"
---
# <a name="safelessthanequals"></a>SafeLessThanEquals
2 つの数値を比較します。  
  
## <a name="syntax"></a>構文  
  
```  
template <typename T, typename U>  
inline bool SafeLessThanEquals (  
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
 **true**場合*t*に等しいまたはそれよりも小さい*u*。 そうしないと**false**します。  
  
## <a name="remarks"></a>Remarks  
 **SafeLessThanEquals** 2 つの異なる型の数値を比較することにより、正規表現の比較演算子を拡張します。  
  
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
 [SafeLessThan](../windows/safelessthan.md)   
 [SafeGreaterThanEquals](../windows/safegreaterthanequals.md)