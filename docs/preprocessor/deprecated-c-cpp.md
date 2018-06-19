---
title: 非推奨 (C/C++) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- vc-pragma.deprecated
- deprecated_CPP
dev_langs:
- C++
helpviewer_keywords:
- deprecated pragma
- pragmas, deprecated
ms.assetid: 9c046f12-7875-499a-8d5d-12f8642fed2d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2280d5245292625bfc29815475eaca63d4d500bd
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33839820"
---
# <a name="deprecated-cc"></a>非推奨 (C/C++)
**廃止**プラグマを指定すること、関数、型、またはその他の識別子は不要になったではサポート、将来のリリースまたは使用できなくします。  
> [!NOTE]
> C++ 14 に関する情報の`[[deprecated]]`属性では、Microsoft declspec またはプラグマを vs 属性、およびそれを使用する場合のガイダンスを参照してください[C++ の標準属性](../cpp/attributes.md)属性。
  
## <a name="syntax"></a>構文  
  
```  
#pragma deprecated( identifier1 [,identifier2, ...] )  
```  
  
## <a name="remarks"></a>コメント  
 コンパイラがで指定された識別子を検出した場合、**廃止**プラグマ、コンパイラの警告を発行[C4995](../error-messages/compiler-warnings/compiler-warning-level-3-c4995.md)です。   
  
 マクロ名の使用を避けることができます。 マクロ名を引用符で囲んで配置します。そうしないと、マクロ展開が発生します。  
  
 **廃止**プラグマは、すべての一致する識別子に動作し、考慮されていない署名アカウント、オーバー ロードされた関数の特定のバージョンの非推奨化に最適なオプションではありません。 スコープ内に取り込まを任意の一致する関数名は、警告をトリガーします。

  C++ 14 を使用することをお勧め`[[deprecated]]`の代わりに、可能であれば、属性、**廃止**プラグマ。 Microsoft 固有[__declspec(deprecated)](../cpp/deprecated-cpp.md)宣言修飾子はより多くの場合の方が適切ではまた、**廃止**プラグマ。 `[[deprecated]]`属性と`__declspec(deprecated)`修飾子を使用すると、オーバー ロードされた関数の特定のフォームの非推奨の状態を指定できます。 診断の警告にのみ表示されます、特定のオーバー ロードされた関数への参照で、属性またはに修飾子を適用します。  
  
## <a name="example"></a>例  
  
```  
// pragma_directive_deprecated.cpp  
// compile with: /W3  
#include <stdio.h>  
void func1(void) {  
}  
  
void func2(void) {  
}  
  
int main() {  
   func1();  
   func2();  
   #pragma deprecated(func1, func2)  
   func1();   // C4995  
   func2();   // C4995  
}  
```  
  
 次のサンプルでは、クラスの使用を避ける方法を示します。  
  
```  
// pragma_directive_deprecated2.cpp  
// compile with: /W3  
#pragma deprecated(X)  
class X {  // C4995  
public:  
   void f(){}  
};  
  
int main() {  
   X x;   // C4995  
}  
```  
  
## <a name="see-also"></a>関連項目  
 [プラグマ ディレクティブと __Pragma キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)