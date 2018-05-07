---
title: コンパイラ エラー C2868 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2868
dev_langs:
- C++
helpviewer_keywords:
- C2868
ms.assetid: 6ff5837b-e66d-44d1-9d17-80af35e08d08
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 84465453ca7a1d76a9dd6b199232384c2ef9124b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2868"></a>コンパイラ エラー C2868  
  
> '*識別子*': using 宣言の構文上の誤りです予期される修飾名。  
  
A[宣言を使用して](../../cpp/using-declaration.md)が必要です、*修飾名*、スコープ演算子 (`::`) 区切られた識別子名で終わる一連の名前空間、クラス、または列挙型名。 1 つのスコープ解決演算子は、グローバル名前空間から名前を導入するために可能性があります。  
  
## <a name="example"></a>例  
  
次の例では、C2868 を生成し、正しい使用法も示しています。  
  
```cpp  
// C2868.cpp  
class X {  
public:  
   int i;  
};  
  
class Y : X {  
public:  
   using X::i;   // OK  
};  
  
int main() {  
   using X;   // C2868  
}  
```