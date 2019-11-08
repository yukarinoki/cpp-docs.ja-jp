---
title: __int8、__int16、__int32、__int64
ms.date: 10/09/2018
f1_keywords:
- __int8_cpp
- __int16_cpp
- __int32_cpp
- __int64_cpp
- __int8
- __int16
- __int32
- __int64
- _int8
- _int16
- _int32
- _int64
helpviewer_keywords:
- __int16 keyword [C++]
- integer data type [C++], integer types in C++
- __int32 keyword [C++]
- integer types [C++]
- __int8 keyword [C++]
- __int64 keyword [C++]
ms.assetid: 8e384602-2578-4980-8cc8-da63842356b2
ms.openlocfilehash: b765eabcac3f9643c0cae78fefb6ce8231669ffc
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62183455"
---
# <a name="int8-int16-int32-int64"></a>__int8、__int16、__int32、__int64

**Microsoft 固有の仕様**

Microsoft C/C++ の機能では、サイズ設定された整数型をサポートします。 使用して、8、16、32 ビットまたは 64 ビット整数変数を宣言することができます、 **_ _int**<em>n</em>指定子は、入力場所*n*が 8、16、32 ビットまたは 64 です。

次の例は、サイズ設定された整数のこれらの型のそれぞれに 1 つの変数を宣言しています。

```cpp
__int8 nSmall;      // Declares 8-bit integer
__int16 nMedium;    // Declares 16-bit integer
__int32 nLarge;     // Declares 32-bit integer
__int64 nHuge;      // Declares 64-bit integer
```

種類 **_ _int8**、 **_ _int16**、および **_ _int32**はシノニム、ANSI 型が同じサイズのいずれかとは、同じように動作する移植可能なコードを記述するために役立ちます複数のプラットフォームです。 **_ _Int8**データ型は型と同義です**char**、 **_ _int16**型と同義です**short**、および **_ _int32。** 型と同義です**int**します。**_ _Int64**型は型と同義です。 **long**します。

以前のバージョンとの互換性のため **_int8**、 **_ _int16**、 **_ _int32**、および **_ _int64**のシノニムで **_ _int8**、 **_ _int16**、 **_ _int32**、および **_ _int64**しない限り、コンパイラ オプション[/Za\(言語を無効にします。拡張機能)](../build/reference/za-ze-disable-language-extensions.md)を指定します。

## <a name="example"></a>例

次の例を示します、_ _int*xx*パラメーターに昇格されます**int**:

```cpp
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

[キーワード](../cpp/keywords-cpp.md)<br/>
[基本的な型](../cpp/fundamental-types-cpp.md)<br/>
[データ型の範囲](../cpp/data-type-ranges.md)<br/>
