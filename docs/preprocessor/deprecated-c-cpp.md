---
title: 非推奨の (C++) |Microsoft Docs
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
ms.openlocfilehash: d51ee23ab4e4be9cf24b913cb0c4ffa325a9bbf5
ms.sourcegitcommit: d4c803bd3a684d7951bf88dcecf1f14af43ae411
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/10/2018
ms.locfileid: "42540858"
---
# <a name="deprecated-cc"></a>非推奨 (C/C++)
**非推奨とされます**関数、型、またはその他の識別子が可能性があります、将来にサポートされなくことを示すプラグマによりリリースかを使用する必要があります。  
> [!NOTE]
> C++ 14 について`[[deprecated]]`属性、およびそれを使用するタイミングに関するガイダンスは、vs を Microsoft declspec または pragma 属性を参照してください[C++ の標準属性](../cpp/attributes.md)属性。
  
## <a name="syntax"></a>構文  
  
```  
#pragma deprecated( identifier1 [,identifier2, ...] )  
```  
  
## <a name="remarks"></a>Remarks  
コンパイラがで指定された識別子を検出した場合、**非推奨とされます**プラグマ、コンパイラの警告を発行[C4995](../error-messages/compiler-warnings/compiler-warning-level-3-c4995.md)します。   
  
マクロ名の使用を避けることができます。 マクロ名を引用符で囲んで配置します。そうしないと、マクロ展開が発生します。  
  
**非推奨とされます**プラグマは、すべての一致する識別子で機能し、アカウントに署名を受け取らない、オーバー ロードされた関数の特定のバージョンを非推奨の最適なオプションではありません。 スコープに取り込まれるすべての一致する関数名は、警告をトリガーします。

C++ 14 を使用することをお勧めします。`[[deprecated]]`属性は、可能であれば、の代わりに、**非推奨とされます**プラグマ。 Microsoft 固有[__declspec(deprecated)](../cpp/deprecated-cpp.md)宣言修飾子はより多くの場合の方が適切でも、**非推奨とされます**プラグマ。 `[[deprecated]]`属性と`__declspec(deprecated)`修飾子を使用すると、オーバー ロードされた関数の特定のフォームの非推奨のステータスを指定できます。 診断の警告のみに表示されます、特定のオーバー ロードされた関数への参照属性または修飾子に適用されます。  
  
## <a name="example"></a>例  
  
```cpp  
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
  
```cpp  
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