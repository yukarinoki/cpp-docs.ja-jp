---
title: _ _int8、_ _int16、_ _int32、_ _int64 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- __int8_cpp
- __int16_cpp
- __int32_cpp
- __int64_cpp
dev_langs:
- C++
helpviewer_keywords:
- __int16 keyword [C++]
- integer data type [C++], integer types in C++
- __int32 keyword [C++]
- integer types [C++]
- __int8 keyword [C++]
- __int64 keyword [C++]
ms.assetid: 8e384602-2578-4980-8cc8-da63842356b2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8083d37d2526820ccd75104f9ee8a748eb5d33bc
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="int8-int16-int32-int64"></a>__int8、__int16、__int32、__int64
## <a name="microsoft-specific"></a>Microsoft 固有の仕様  
 Microsoft C/C++ の機能では、サイズ設定された整数型をサポートします。 使用して、8、16、32 ビットまたは 64 ビット整数変数を宣言することができます、**_ _int * * * n*指定子を入力する場所*n*が 8、16、32、または 64 です。  
  
 次の例は、サイズ設定された整数のこれらの型のそれぞれに 1 つの変数を宣言しています。  
  
```  
__int8 nSmall;      // Declares 8-bit integer  
__int16 nMedium;    // Declares 16-bit integer  
__int32 nLarge;     // Declares 32-bit integer  
__int64 nHuge;      // Declares 64-bit integer  
```  
  
 型 `__int8`、`__int16`、および `__int32` は、同じサイズを持つ ANSI 型のシノニムであり、複数のプラットフォームで同じように動作する移植性のあるコードを作成する場合に便利です。 `__int8`データ型は型と同義`char`、`__int16`型と同義です**短い**、および`__int32`型と同義です`int`です。 `__int64`型は型と同義`long long`です。  
  
## <a name="example"></a>例  
 次の例を示します、_ _int*xx*パラメーターに昇格されます`int`:  
  
```  
// sized_int_types.cpp  
  
#include <stdio.h>  
  
void func(int i) {  
    printf_s("%s\n", __FUNCTION__);  
}  
  
int main()  
{  
    __int8 i8 = 100;  
    func(i8);   // no void func(__int8 i8) function  
                // __int8 will be promoted to int  
}  
```  
  
```Output  
func  
```  
  
**Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [キーワード](../cpp/keywords-cpp.md)   
 [基本型](../cpp/fundamental-types-cpp.md)   
 [データ型の範囲](../cpp/data-type-ranges.md)