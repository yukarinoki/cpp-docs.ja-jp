---
title: '方法: C++/CLI で列挙型を定義および使用する'
ms.date: 11/04/2016
helpviewer_keywords:
- enum class, specifying underlying types
ms.assetid: df8f2b91-b9d2-4fab-9be4-b1d58b8bc570
ms.openlocfilehash: 68f8e113f6199d3b320bc6d241ee3396d2b70a1a
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2019
ms.locfileid: "79544983"
---
# <a name="how-to-define-and-consume-enums-in-ccli"></a>方法: C++/CLI で列挙型を定義および使用する

このトピックでは、 C++/cli の列挙型について説明します。

## <a name="specifying-the-underlying-type-of-an-enum"></a>列挙型の基になる型の指定

既定では、列挙型の基になる型は `int`です。  ただし、`int`、`short`、`long`、`__int32`、または `__int64`の符号付きまたは符号なしの形式を指定することもできます。  `char` を使用することもできます。

```cpp
// mcppv2_enum_3.cpp
// compile with: /clr
public enum class day_char : char {sun, mon, tue, wed, thu, fri, sat};

int main() {
   // fully qualified names, enumerator not injected into scope
   day_char d = day_char::sun, e = day_char::mon;
   System::Console::WriteLine(d);
   char f = (char)d;
   System::Console::WriteLine(f);
   f = (char)e;
   System::Console::WriteLine(f);
   e = day_char::tue;
   f = (char)e;
   System::Console::WriteLine(f);
}
```

**出力**

```Output
sun
0
1
2
```

## <a name="how-to-convert-between-managed-and-standard-enumerations"></a>マネージ列挙型と標準列挙型の間で変換を行う方法

列挙型と整数型の間で標準変換は行われません。キャストが必要です。

```cpp
// mcppv2_enum_4.cpp
// compile with: /clr
enum class day {sun, mon, tue, wed, thu, fri, sat};
enum {sun, mon, tue, wed, thu, fri, sat} day2; // unnamed std enum

int main() {
   day a = day::sun;
   day2 = sun;
   if ((int)a == day2)
   // or...
   // if (a == (day)day2)
      System::Console::WriteLine("a and day2 are the same");
   else
      System::Console::WriteLine("a and day2 are not the same");
}
```

**出力**

```Output
a and day2 are the same
```

## <a name="operators-and-enums"></a>演算子と列挙型

次の演算子は、 C++/cli の列挙型で有効です。

|演算子|
|--------------|
|= =! = \< > \<= > =|
|+ -|
|&#124; ^ & ~|
|++ --|
|sizeof|

演算子&#124; ^ & ~ + +--は、ブール値を含まない、基になる整数型の列挙型に対してのみ定義されています。  両方のオペランドは列挙型である必要があります。

コンパイラは、列挙演算の結果を静的または動的にチェックしません。演算を実行すると、列挙型の有効な列挙子の範囲内にない値が生成される可能性があります。

> [!NOTE]
>  C++ 11 では、/Cli のC++マネージ列挙型クラスと大幅に異なるアンマネージコードで列挙型クラス型が導入されました。 特に、C++ 11 列挙型クラス型は、/Cli のC++マネージ列挙型クラス型と同じ演算子をサポートしてC++いません。また、/cli ソースコードは、アンマネージ (c++ 11) 列挙型クラス宣言と区別するために、マネージ列挙型クラス宣言でアクセシビリティ指定子を提供する必要があります。 /Cli、 C++/cx、および c++ 11 C++の列挙型クラスの詳細については、「 [enum class](../extensions/enum-class-cpp-component-extensions.md)」を参照してください。

```cpp
// mcppv2_enum_5.cpp
// compile with: /clr
private enum class E { a, b } e, mask;
int main() {
   if ( e & mask )   // C2451 no E->bool conversion
      ;

   if ( ( e & mask ) != 0 )   // C3063 no operator!= (E, int)
      ;

   if ( ( e & mask ) != E() )   // OK
      ;
}
```

```cpp
// mcppv2_enum_6.cpp
// compile with: /clr
private enum class day : int {sun, mon};
enum : bool {sun = true, mon = false} day2;

int main() {
   day a = day::sun, b = day::mon;
   day2 = sun;

   System::Console::WriteLine(sizeof(a));
   System::Console::WriteLine(sizeof(day2));
   a++;
   System::Console::WriteLine(a == b);
}
```

**出力**

```Output
4
1
True
```

## <a name="see-also"></a>参照

[enum クラス](../extensions/enum-class-cpp-component-extensions.md)
