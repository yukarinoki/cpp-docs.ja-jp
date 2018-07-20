---
title: SafeLessThan |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- SafeLessThan
dev_langs:
- C++
helpviewer_keywords:
- SafeLessThan function
ms.assetid: 9d85bc0d-8d94-4d59-9b72-ef3c63a120a0
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ed6f114d13b006425cd3e94e898b2fe924ec732d
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33888424"
---
# <a name="safelessthan"></a>SafeLessThan
1 つの数値が他よりも小さいかどうかを判断します。  
  
## <a name="syntax"></a>構文  
  
```  
template<typename T, typename U>  
inline bool SafeLessThan (  
   const T t,  
   const U u  
) throw ();  
```  
  
#### <a name="parameters"></a>パラメーター  
 [入力] `t`  
 最初の数値。 T 型でなければなりません  
  
 [入力] `u`  
 2 番目の数値。 U 型です。 これでなければなりません  
  
## <a name="return-value"></a>戻り値  
 `true` 場合`t`はより小さい`u`それ以外の`false`します。  
  
## <a name="remarks"></a>コメント  
 このメソッドは、ために、標準的な比較演算子を強化`SafeLessThan`数の 2 つの異なる型を比較することができます。  
  
 このメソッドの一部である[SafeInt ライブラリ](../windows/safeint-library.md)とは、単一の比較操作のインスタンスを作成せず、 [SafeInt クラス](../windows/safeint-class.md)です。  
  
> [!NOTE]
>  このメソッドは、単一の数値演算を保護する必要がありますにのみ使用する必要があります。 使用する必要があります複数の操作がある場合、`SafeInt`個別スタンドアロン関数を呼び出すのではなく、クラスです。  
  
 テンプレート型 T および U の詳細については、次を参照してください。 [SafeInt 関数](../windows/safeint-functions.md)です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** safeint.h  
  
 **Namespace:** Microsoft::Utilities  
  
## <a name="see-also"></a>関連項目  
 [SafeInt 関数](../windows/safeint-functions.md)   
 [SafeInt ライブラリ](../windows/safeint-library.md)   
 [SafeInt クラス](../windows/safeint-class.md)   
 [SafeLessThanEquals](../windows/safelessthanequals.md)   
 [SafeGreaterThan](../windows/safegreaterthan.md)   
 [SafeGreaterThanEquals](../windows/safegreaterthanequals.md)