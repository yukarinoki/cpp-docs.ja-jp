---
title: '単項プラス演算子と否定演算子: +、- |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- +
- '-'
dev_langs:
- C++
helpviewer_keywords:
- unary operators [C++], plus
- '- operator'
- negation operator
- + operator [C++], unary operators
- + operator
ms.assetid: 2c58c4f4-0d92-4ae3-9d0c-1a6157875cc1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1441337275ac07b0d1ba39e8bfa34e7165f87f82
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="unary-plus-and-negation-operators--and--"></a>単項加算演算子と否定演算子: + および -
## <a name="syntax"></a>構文  
  
```  
  
+ cast-expression  
```  
  
```  
  
- cast-expression  
```  
  
## <a name="-operator"></a>+ 演算子  
 単項プラス演算子の結果 (**+**)、オペランドの値です。 単項プラス演算子のオペランドは数値型である必要があります。  
  
 整数の上位変換が整数オペランドに対して実行されます。 結果の型は、オペランドの上位変換先の型です。 したがって、式 `+ch` (`ch` が `char` 型) は、結果が `int` 型になります。値は変更されません。 参照してください[標準変換](standard-conversions.md)昇格を実行する方法の詳細についてはします。  
  
## <a name="--operator"></a>- 演算子  
 単項否定演算子 (**-**)、オペランドの負数を生成します。 単項否定演算子のオペランドには数値型を指定する必要があります。  
  
 整数の上位変換は、整数オペランドに対して実行され、結果の型は、そのオペランドが昇格される型になります。 参照してください[標準変換](standard-conversions.md)昇格を実行する方法の詳細についてはします。  
  
## <a name="microsoft-specific"></a>Microsoft 固有の仕様  
 符号なし数値の単項否定演算は、2^n からオペランドの値を減算することによって実行されます。この n は、指定した符号なし型のオブジェクトのビット数です。
  
## <a name="see-also"></a>関連項目  
 [単項演算子を含む式](../cpp/expressions-with-unary-operators.md)   
 [C++ の組み込み演算子、優先順位と結合規則](../cpp/cpp-built-in-operators-precedence-and-associativity.md)
