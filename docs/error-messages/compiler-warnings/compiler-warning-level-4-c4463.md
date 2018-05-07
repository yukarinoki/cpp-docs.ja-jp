---
title: コンパイラの警告 (レベル 4) C4463 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4463
dev_langs:
- C++
helpviewer_keywords:
- C4463
ms.assetid: a07ae70c-db4e-472b-8b58-9137d9997323
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3c13e0a79c667ecedbf3fd065338892d3af9c2ee
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-4-c4463"></a>コンパイラの警告 (レベル 4) C4463  
  
> オーバーフローです。割り当てる*値*のみからの値を保持できるビット フィールドに*low_value*に*high_value*  
  
割り当てられている*値*ビット フィールドを保持できる値の範囲外です。 符号付きビット フィールド型は、符号ビットの高位を使用できるよう*n*ビット フィールドのサイズ、範囲が符号付きビット フィールドは-2<sup>n-1</sup> 2<sup>n-1</sup>-1 で、署名されていないときにビット フィールドが 0 ~ 2 の範囲にある<sup>n</sup>-1 です。  
  
## <a name="example"></a>例  
  
この例では生成しようとする型のビット フィールドに 3 の値を割り当てるため C4463`int`サイズが 2 を持つ-2 ~ 1 の範囲。  
  
この問題を解決するには、許容範囲に存在するものを割り当てられた値を変更できます。 宣言の型を変更するにはビット フィールドを 0 ~ 3 の範囲で符号なしの値を保持する場合は`unsigned`します。 フィールドを範囲-4 ~ 3 の値を保持する場合は 3 に、ビット フィールドのサイズを変更できます。  
  
```cpp  
// C4463_overflow.cpp
// compile with: cl /W4 /EHsc C4463_overflow.cpp
struct S { 
    int x : 2; // int type treats high-order bit as sign
}; 

int main() { 
    S s; 
    s.x = 3; // warning C4463: overflow; assigning 3 
    // to bit-field that can only hold values from -2 to 1 
    // To fix, change assigned value to fit in range,
    // increase size of bitfield, and/or change base type 
    // to unsigned.
} 
```  
