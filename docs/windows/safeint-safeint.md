---
title: Safeint::safeint |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- SafeInt::SafeInt
- SafeInt
- SafeInt.SafeInt
dev_langs:
- C++
helpviewer_keywords:
- SafeInt class, constructor
ms.assetid: 39e6f632-a396-40e6-9ece-cc3d4c5a78ef
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c7154349105c1953ad314b7928e7be8385179c42
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33888748"
---
# <a name="safeintsafeint"></a>SafeInt::SafeInt
`SafeInt` オブジェクトを構築します。  
  
## <a name="syntax"></a>構文  
  
```  
SafeInt() throw  
  
SafeInt (  
   const T& i  
) throw ()  
  
SafeInt (  
   bool b  
) throw ()  
  
template <typename U>  
SafeInt (  
   const SafeInt <U, E>& u  
)  
  
I template <typename U>  
SafeInt (  
   const U& i  
)  
```  
  
#### <a name="parameters"></a>パラメーター  
 [入力] `i`  
 新しい値`SafeInt`オブジェクト。 これは、コンス トラクターによって型 T、または U のパラメーターでなければなりません。  
  
 [入力] `b`  
 新しいブール値`SafeInt`オブジェクト。  
  
 [入力] `u`  
 A`SafeInt`は u 型です。新しい`SafeInt`オブジェクトと同じ値になります`u`T 型になりますが、  
  
 U  
 格納されたデータの種類、`SafeInt`です。 ブール値を文字、または整数のいずれかの型を指定できます。 型の場合は、整数、符号付きしたりできる符号なし 8 と 64 ビットの間であるとします。  
  
## <a name="remarks"></a>コメント  
 テンプレートの種類の詳細については`T`と`E`を参照してください[SafeInt クラス](../windows/safeint-class.md)です。  
  
 入力パラメーター、コンス トラクターを`i`または`u`、ブール値を文字、または整数型である必要があります。 パラメーターの別の型の場合は、`SafeInt`クラス[static_assert](../cpp/static-assert.md)を無効な入力パラメーターを示します。  
  
 テンプレートの種類を使用するコンス トラクター`U`で指定された型に、入力パラメーターを自動的に変換`T`です。 `SafeInt`クラスは、データを失うことがなくデータを変換します。 エラー ハンドラーに報告`E`、データ型に変換できない場合`T`データ損失なし。  
  
 作成する場合、`SafeInt`ブール型のパラメーターの値をすぐに初期化する必要があります。 構築することはできません、`SafeInt`コードを使用して`SafeInt<bool> sb;`です。 これにより、コンパイル エラーが生成されます。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** safeint.h  
  
 **Namespace:** msl::utilities  
  
## <a name="see-also"></a>関連項目  
 [SafeInt ライブラリ](../windows/safeint-library.md)   
 [SafeInt クラス](../windows/safeint-class.md)   
 [SafeIntException クラス](../windows/safeintexception-class.md)