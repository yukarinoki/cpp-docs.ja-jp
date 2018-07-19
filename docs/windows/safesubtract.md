---
title: SafeSubtract |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- SafeSubtract
dev_langs:
- C++
helpviewer_keywords:
- SafeSubtract function
ms.assetid: c2712ddc-173f-46a1-b09c-e7ebbd9e68b2
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 300959fe64d280ff3e2c19fd579e8f447a2402eb
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33889230"
---
# <a name="safesubtract"></a>SafeSubtract
オーバーフローを防止する方法の 2 つの数値を減算します。  
  
## <a name="syntax"></a>構文  
  
```  
template<typename T, typename U>  
inline bool SafeSubtract (  
   T t,  
   U u,  
   T& result  
) throw ();  
```  
  
#### <a name="parameters"></a>パラメーター  
 [入力] `t`  
 減算の最初の数。 T 型でなければなりません  
  
 [入力] `u`  
 減算する数`t`です。 U 型です。 これでなければなりません  
  
 [出力] `result`  
 パラメーターで`SafeSubtract`結果を格納します。  
  
## <a name="return-value"></a>戻り値  
 `true` エラーが発生しない場合です。`false`場合は、エラーが発生します。  
  
## <a name="remarks"></a>コメント  
 このメソッドの一部である[SafeInt ライブラリ](../windows/safeint-library.md)のインスタンスを作成することがなく 1 つの減算演算のものでは、 [SafeInt クラス](../windows/safeint-class.md)です。  
  
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
 [SafeAdd](../windows/safeadd.md)