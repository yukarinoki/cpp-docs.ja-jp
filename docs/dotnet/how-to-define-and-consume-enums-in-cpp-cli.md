---
title: '方法: C++/CLI で列挙型を定義および使用する'
ms.date: 11/04/2016
helpviewer_keywords:
- enum class, specifying underlying types
ms.assetid: df8f2b91-b9d2-4fab-9be4-b1d58b8bc570
ms.openlocfilehash: f09bb6e9fac30b72c3c4e0682c3d90f2ea9f8760
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87216415"
---
# <a name="how-to-define-and-consume-enums-in-ccli"></a>方法: C++/CLI で列挙型を定義および使用する

このトピックでは、C++/CLI の列挙型について説明します。

## <a name="specifying-the-underlying-type-of-an-enum"></a>列挙型の基になる型の指定

既定では、列挙型の基になる型は **`int`** です。  ただし、型は、、、、 **`int`** **`short`** **`long`** **`__int32`** 、またはの符号付きまたは符号なし形式として指定でき **`__int64`** ます。  を使用することもでき **`char`** ます。

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

次の演算子は、C++/CLI の列挙型で有効です。

|演算子|
|--------------|
|== != \< >\<= >=|
|+ -|
|&#124; ^ & ~|
|++ --|
|sizeof|

演算子 &#124; ^ & ~ + +--は、ブール値を含まない、基になる整数型の列挙型に対してのみ定義されます。  両方のオペランドは列挙型である必要があります。

コンパイラは、列挙演算の結果を静的または動的にチェックしません。演算を実行すると、列挙型の有効な列挙子の範囲内にない値が生成される可能性があります。

> [!NOTE]
> C++ 11 では、C++/CLI のマネージ列挙型クラスと大幅に異なるアンマネージコードで列挙型クラス型が導入されました。 特に、c++ 11 列挙型クラス型は、C++/CLI ではマネージ列挙型クラス型と同じ演算子をサポートしていません。また、C++/CLI ソースコードは、アンマネージ (C++ 11) 列挙型クラス宣言と区別するために、マネージ列挙型クラス宣言でアクセシビリティ指定子を提供する必要があります。 C++/CLI、C++/CX、および C++ 11 の列挙型クラスの詳細については、「 [enum クラス](../extensions/enum-class-cpp-component-extensions.md)」を参照してください。

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

## <a name="see-also"></a>関連項目

[enum クラス](../extensions/enum-class-cpp-component-extensions.md)
