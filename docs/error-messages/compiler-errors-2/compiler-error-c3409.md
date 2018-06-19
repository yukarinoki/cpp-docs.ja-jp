---
title: コンパイラ エラー C3409 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3409
dev_langs:
- C++
helpviewer_keywords:
- C3409
ms.assetid: e372d9fa-230c-4b28-b6d3-6ad81ccf9dbb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1964cffd0593e87a790befd8a76ae13847f2058d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33257271"
---
# <a name="compiler-error-c3409"></a>コンパイラ エラー C3409
空の属性ブロックは許可されていません  
  
 角かっこは、コンパイラによってとして解釈されていましたが[属性](../../windows/cpp-attributes-reference.md)ブロックがない属性が見つかりませんでした。  
  
 コンパイラは、ラムダ式の定義の一部として角かっこを使用すると、このエラーを発生する可能性があります。 このエラーは、コンパイラは角かっこはラムダ式または属性ブロックの定義の一部であるかどうかを判断できないときに発生します。 ラムダ式について詳しくは、「[ラムダ式](../../cpp/lambda-expressions-in-cpp.md)」をご覧ください。  
  
### <a name="to-correct-this-error"></a>このエラーを解決するには  
  
1.  角かっこを含める場合は、属性ブロックです。  
  
    1.  属性ブロックに 1 つまたは複数の属性を提供します。  
  
    2.  属性ブロックを削除します。  
  
2.  角かっこを含める場合は、ラムダ式です。  
  
    1.  ラムダ式が有効な構文の規則に従うことを確認します。  
  
         ラムダ式の構文の詳細については、次を参照してください。[ラムダ式の構文](../../cpp/lambda-expression-syntax.md)です。  
  
    2.  
  
## <a name="example"></a>例  
 次の例では、C3409 が生成されます。  
  
```  
// C3409.cpp  
// compile with: /c  
#include <windows.h>  
[]   // C3409  
class a {};  
  
// OK  
[object, uuid("00000000-0000-0000-0000-000000000000")]  
__interface x {};  
  
[coclass, uuid("00000000-0000-0000-0000-000000000001")]  
class b : public x {};  
```  
  
## <a name="example"></a>例  
 ラムダ式を使用するために次の例が c3409、`mutable`仕様では、パラメーター リストは提供しません。 コンパイラでは、角かっこはラムダ式または属性ブロックの定義の一部であるかどうかを判断できません。  
  
```  
// C3409b.cpp  
  
int main()  
{  
   [] mutable {}();  
}  
```  
  
## <a name="see-also"></a>関連項目  
 [属性](../../windows/cpp-attributes-reference.md)   
 [ラムダ式](../../cpp/lambda-expressions-in-cpp.md)   
 [ラムダ式の構文](../../cpp/lambda-expression-syntax.md)