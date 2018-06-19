---
title: SafeLessThanEquals |Microsoft ドキュメント
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
ms.openlocfilehash: dd783f5d611b6055c542f56d04e2249b71b31218
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33892814"
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
  
#### <a name="parameters"></a>パラメーター  
 [入力] `t`  
 比較する最初の数。 T 型でなければなりません  
  
 [入力] `u`  
 比較する 2 番目の数値。 U 型です。 これでなければなりません  
  
## <a name="return-value"></a>戻り値  
 `true` 場合`t`と同じかそれよりも少ない`u`それ以外の`false`します。  
  
## <a name="remarks"></a>コメント  
 `SafeLessThanEquals` 2 つの異なる型の数値を比較することにより、正規の比較演算子を拡張します。  
  
 このメソッドの一部である[SafeInt ライブラリ](../windows/safeint-library.md)とは、単一の比較操作のインスタンスを作成せず、 [SafeInt クラス](../windows/safeint-class.md)です。  
  
> [!NOTE]
>  このメソッドは、単一の数値演算を保護する必要がありますにのみ使用する必要があります。 使用する必要があります複数の操作がある場合、`SafeInt`個々 のスタンドアロン関数の呼び出しではなくクラスです。  
  
 テンプレート型 T および U の詳細については、次を参照してください。 [SafeInt 関数](../windows/safeint-functions.md)です。  
  
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