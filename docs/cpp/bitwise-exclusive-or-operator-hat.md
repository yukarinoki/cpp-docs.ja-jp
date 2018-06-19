---
title: 'ビットごとの排他的 OR 演算子: ^ |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- operators [C++], bitwise
- exclusive OR operator
- XOR operator
- bitwise operators [C++], OR operator
- ^ operator
- OR operator [C++], bitwise exclusive
- operators [C++], logical
ms.assetid: f9185d85-65d5-4f64-a6d6-679758d52217
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0d080fa28e8f70cb6a4086709c4a5fc6215c4519
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32409853"
---
# <a name="bitwise-exclusive-or-operator-"></a>ビット処理排他的 OR 演算子: ^
## <a name="syntax"></a>構文  
  
```  
expression ^ expression  
```  
  
## <a name="remarks"></a>コメント  
ビットごとの排他的 OR 演算子 (**^**)、2 番目のオペランドの対応するビットを最初のオペランドの各ビットと比較します。 一方のビットが 0 でもう一方のビットが 1 の場合、対応する結果のビットは 1 に設定されます。 それ以外の場合は、対応する結果ビットが 0 に設定されます。  
  
ビットごとの排他的 OR 演算子のオペランドは両方とも整数型である必要があります。 通常の算術変換は、「[標準変換](standard-conversions.md)オペランドに適用されます。  
  
## <a name="operator-keyword-for-"></a>^ の演算子キーワード  
**Xor**演算子に相当するテキストは、  **^** です。 アクセスする方法を次の 2 つが、 **xor**をプログラムで演算子: ヘッダー ファイルをインクルード`iso646.h`、コンパイル時に、または、 [/Za](../build/reference/za-ze-disable-language-extensions.md) (言語の拡張機能を無効にする) コンパイラ オプション。  
  
## <a name="example"></a>例  
  
```cpp  
// expre_Bitwise_Exclusive_OR_Operator.cpp  
// compile with: /EHsc  
// Demonstrate bitwise exclusive OR  
#include <iostream>  
using namespace std;  
int main() {  
   unsigned short a = 0x5555;      // pattern 0101 ...  
   unsigned short b = 0xFFFF;      // pattern 1111 ...  
  
   cout  << hex << ( a ^ b ) << endl;   // prints "aaaa" pattern 1010 ...  
}  
```  
  
## <a name="see-also"></a>関連項目  
 [C++ の組み込み演算子、優先順位と結合規則](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   


