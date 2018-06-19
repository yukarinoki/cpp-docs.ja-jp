---
title: 関数テンプレート呼び出しのオーバー ロード解決 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- function templates overload resolution
ms.assetid: a2918748-2cbb-4fc6-a176-e256f120bee4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3d4a0e2867c5057eb5808c4d39687961eabba6dd
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32420029"
---
# <a name="overload-resolution-of-function-template-calls"></a>関数テンプレート呼び出しのオーバーロード解決
関数テンプレートは同じ名前の非テンプレート関数をオーバーロードできます。 このシナリオでは、一意の特殊化により関数テンプレートをインスタンス化するため、関数呼び出しは、最初にテンプレート引数の推論を使用して解決されます。 テンプレート引数の推論が失敗した場合、他の関数オーバーロードが呼び出しを解決すると見なされます。 これらのオーバーロード (候補の集合とも呼ばれます) には、非テンプレート関数、およびその他のインスタンス化された関数テンプレートが含まれています。 テンプレート引数の推論に成功すると、オーバーロード解決の規則に従って最適な一致項目を決定するために、生成された関数は他の関数と比較されます。 詳細については、次を参照してください。[関数のオーバー ロード](function-overloading.md)です。  
  
## <a name="example"></a>例

 非テンプレート関数がテンプレート関数と同等に一致する場合、次の例の呼び出し `f(1, 1)` のように、(テンプレート引数が明示的に指定されていない限り) 非テンプレート関数が選択されます。  
  
```cpp
// template_name_resolution9.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
  
void f(int, int) { cout << "f(int, int)" << endl; }  
void f(char, char) { cout << "f(char, char)" << endl; }  
  
template <class T1, class T2>  
void f(T1, T2)  
{  
   cout << "void f(T1, T2)" << endl;  
};  
  
int main()  
{  
   f(1, 1);   // Equally good match; choose the nontemplate function.  
   f('a', 1); // Chooses the template function.  
   f<int, int>(2, 2);  // Template arguments explicitly specified.  
}  
```  
  
```Output  
f(int, int)  
void f(T1, T2)  
void f(T1, T2)  
```  
  
## <a name="example"></a>例

 非テンプレート関数が変換を必要とする場合は、正確に一致するテンプレート関数が推奨されます。次に例を示します。  
  
```cpp
// template_name_resolution10.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
  
void f(int, int) { cout << "f(int, int)" << endl; }  
  
template <class T1, class T2>  
void f(T1, T2)  
{  
   cout << "void f(T1, T2)" << endl;  
};  
  
int main()  
{  
   long l = 0;  
   int i = 0;  
   // Call the template function f(long, int) because f(int, int)  
   // would require a conversion from long to int.  
   f(l, i);  
}  
```  
  
```Output  
void f(T1, T2)  
```  
  
## <a name="see-also"></a>関連項目

 [名前解決](../cpp/templates-and-name-resolution.md)   
 [typename](../cpp/typename.md)   
 
