---
title: C 定数式 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- constant expressions, syntax
- constant expressions
- expressions [C++], constant
ms.assetid: d48a6c47-e44c-4be2-9c8b-7944c7ef8de7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: aaeb7ab79777d247f0bc0b2e6d749d8df5a7f8e9
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="c-constant-expressions"></a>C 定数式
定数式は、実行時ではなくコンパイル時に評価され、定数を使用できるすべての場所で使用できます。 定数式は、その型の表現可能な値の範囲にある定数として評価される必要があります。 定数式のオペランドは、整数定数、文字定数、浮動小数点定数、列挙定数、型キャスト、`sizeof` 式、およびその他の定数式にすることができます。  
  
## <a name="syntax"></a>構文  
 *constant-expression*:  
 *conditional-expression*  
  
 *conditional-expression*:  
 *logical-OR-expression*  
  
 *logical-OR-expression* **?**  *expression* **:**  *conditional-expression*  
  
 *expression*:  
 *assignment-expression*  
  
 *expression* **,**  *assignment-expression*  
  
 *assignment-expression*:  
 *conditional-expression*  
  
 *unary-expression assignment-operator assignment-expression*  
  
 *assignment-operator*: 次のいずれか  
 **= \*= /= %= += -= <\<= >>= &= ^= &#124;=**  
  
 構造体宣言子、列挙子、直接宣言子、直接抽象宣言子、およびラベル付きステートメントの必須でない要素は、必須でない要素の *constant-expression* を含みます。  
  
 整数定数式は、構造体のビット フィールド メンバーのサイズ、列挙定数の値、配列のサイズ、または **case** 定数の値を指定するために使用する必要があります。  
  
 プリプロセッサ ディレクティブに使用される定数式は、追加の制限が適用されます。 そのため、"制限付き定数式" と呼ばれます。 制限付き定数式は、`sizeof` 式、列挙の定数、任意の型への型キャスト、または浮動小数点型の定数を含めることはできません。 ただし、特別な定数式 `defined (`*identifier*`)` を含めることができます。  
  
## <a name="see-also"></a>参照  
 [オペランドおよび式](../c-language/operands-and-expressions.md)