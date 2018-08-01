---
title: 'ビットごとの AND 演算子: &amp; |Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- bitand
dev_langs:
- C++
helpviewer_keywords:
- AND operator
- bitwise operators [C++], AND operator
- '& operator [C++], bitwise operators'
ms.assetid: 76f40de3-c417-47b9-8a77-532f3fc990a5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3122cb3622469adeda3b8c0a2437fe4db7dfca62
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/01/2018
ms.locfileid: "39404214"
---
# <a name="bitwise-and-operator-amp"></a>ビットごとの AND 演算子: &amp;

## <a name="syntax"></a>構文  
  
```
expression & expression  
```
  
## <a name="remarks"></a>Remarks  
 式は、他の and 式、または (以下に言及する型制限に基づき) 等価式、関係式、加算式、乗算式、メンバー式へのポインター、キャスト式、単項式、後置式、または 1 次式である場合もあります。  
  
 ビットごとの AND 演算子 (**&**) 最初のオペランドを 2 番目のオペランドの対応するビットの各ビットと比較します。 両方のビットが 1 の場合、対応する結果のビットは 1 に設定されます。 それ以外の場合は、対応する結果ビットが 0 に設定されます。  
  
 ビットごとの AND 演算子のオペランドは両方とも整数型である必要があります。 通常の算術変換は、「[標準変換](standard-conversions.md)オペランドに適用されます。  
  
## <a name="operator-keyword-for-"></a>演算子キーワード (& a)  
 **Bitand**演算子と等価のテキストは、  **&** します。 アクセスする 2 つの方法がある、 **bitand**プログラムで演算子: ヘッダー ファイルをインクルード`iso646.h`、使用してコンパイル、 [/Za](../build/reference/za-ze-disable-language-extensions.md) (言語拡張を無効にする) コンパイラ オプション。  
  
## <a name="example"></a>例  
  
```cpp 
// expre_Bitwise_AND_Operator.cpp  
// compile with: /EHsc  
// Demonstrate bitwise AND  
#include <iostream>  
using namespace std;  
int main() {  
   unsigned short a = 0xFFFF;      // pattern 1111 ...  
   unsigned short b = 0xAAAA;      // pattern 1010 ...  
  
   cout  << hex << ( a & b ) << endl;   // prints "aaaa", pattern 1010 ...  
}  
```  
  
## <a name="see-also"></a>関連項目  
 [C++ の組み込み演算子、優先順位と結合規則](cpp-built-in-operators-precedence-and-associativity.md)  
 [C++ の組み込み演算子、優先順位と結合規則](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [C ビット処理演算子](../c-language/c-bitwise-operators.md)