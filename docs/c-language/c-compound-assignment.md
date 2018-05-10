---
title: C 複合代入 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- operators [C], assignment
- compound assignment operators
- assignment operators, compound
ms.assetid: db7b5893-cd56-4f1c-9981-5a024200ab63
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7ef882deb6a96117ec572aa675fe80158d192ce7
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="c-compound-assignment"></a>C 複合代入
複合代入演算子は、単純な代入演算子を別の二項演算子と結合します。 複合代入演算子は、追加の演算子で指定された演算を実行し、左オペランドに結果を代入します。 たとえば、次のような複合代入式  
  
```  
  
expression1  
+=  
expression2  
  
```  
  
 は、次の式と同じであると見なすことができます。  
  
```  
  
expression1  
=  
expression1  
+  
expression2  
  
```  
  
 ただし、複合代入式は、展開バージョンと等価ではありません。複合代入式では *expression1* を一度だけ評価しますが、展開バージョンでは *expression1* を加算演算と代入演算で 2 回評価します。  
  
 複合代入演算子のオペランドは、整数型または浮動小数点型である必要があります。 各複合代入演算子は、対応する二項演算子によって実行される変換を実行し、それに応じてそのオペランドの型を制限します。 加算代入 (`+=`) および減算代入 (**-=**) 演算子にはポインター型の左オペランドも含めることができますが、その場合、右オペランドは整数型である必要があります。 複合代入演算の結果は、左側のオペランドの値と型を持ちます。  
  
```  
#define MASK 0xff00  
  
n &= MASK;  
```  
  
 この例では、ビットごとの包括的 AND 演算は `n` と `MASK` で実行され、結果は `n` に割り当てられます。 マニフェスト定数 `MASK` は [#define](../preprocessor/hash-define-directive-c-cpp.md) プリプロセッサ ディレクティブで定義されます。  
  
## <a name="see-also"></a>参照  
 [C の代入演算子](../c-language/c-assignment-operators.md)