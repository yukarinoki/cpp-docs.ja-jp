---
title: 参照型関数の引数 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- arguments [C++], function
- functions [C++], paramters
- function parameters [C++], reference-type
- function arguments [C++], reference-type
- passing parameters [C++], reference-type arguments
ms.assetid: 0a70e831-9e76-46c0-821d-aeba13d73cc0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fad8fc85a37aec80d09ed6df9280a78de0540f01
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/01/2018
ms.locfileid: "39409057"
---
# <a name="reference-type-function-arguments"></a>Reference-Type Function Arguments (参照型関数の引数)
多くの場合、大きなオブジェクトよりも、関数への参照を渡す方が効率的です。 これにより、コンパイラは、オブジェクトへのアクセスに使用される構文を保持しつつ、オブジェクトのアドレスを渡すことができます。 `Date` 構造体を使用する次の例について考えます。  
  
```cpp 
// reference_type_function_arguments.cpp  
struct Date  
{  
short DayOfWeek;  
short Month;  
short Day;  
short Year;  
};  
  
// Create a Julian date of the form DDDYYYY  
// from a Gregorian date.  
long JulianFromGregorian( Date& GDate )  
{  
static int cDaysInMonth[] = {  
31, 28, 31, 30, 31, 30, 31, 31, 30, 31, 30, 31  
   };  
long JDate = 0;  
// Add in days for months already elapsed.  
for ( int i = 0; i < GDate.Month - 1; ++i )  
JDate += cDaysInMonth[i];  
// Add in days for this month.  
JDate += GDate.Day;  
  
// Check for leap year.  
if ( GDate.Year % 100 != 0 && GDate.Year % 4 == 0 )  
JDate++;  
// Add in year.  
JDate *= 10000;  
JDate += GDate.Year;  
  
return JDate;  
}  
  
int main()  
{  
}  
```  
  
 上記のコードは、メンバー選択演算子を使用して参照渡しで渡された構造体のメンバーにアクセスすることを示しています (**.**) ポインター メンバー選択演算子ではなく (**->**)。  
  
 参照型として渡された引数が非ポインター型の構文を観察しますが、ポインター型の 1 つの重要な特性を保持、: として宣言しない限り変更可能な**const**します。 前のコードの意図は `GDate` オブジェクトを変更することではないため、より適切な関数プロトタイプは次のとおりです。  
  
```cpp 
long JulianFromGregorian( const Date& GDate );  
```  
  
 このプロトタイプによって、関数 `JulianFromGregorian` が引数を変更しないことが保証されます。  
  
 標準変換があるために、参照型を受け取るようにプロトタイプ宣言された任意の関数は、代わりに、同じ型のオブジェクトを受け取ることができます*typename*に * typename ***&** します。  
  
## <a name="see-also"></a>関連項目  
 [参照](../cpp/references-cpp.md)