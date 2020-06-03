---
title: '方法: C++/CLI で列挙型を定義および使用する'
ms.date: 11/04/2016
helpviewer_keywords:
- enum class, specifying underlying types
ms.assetid: df8f2b91-b9d2-4fab-9be4-b1d58b8bc570
ms.openlocfilehash: cf3bb23069b2692c0ca4ce270a5b8060195becf7
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370172"
---
# <a name="how-to-define-and-consume-enums-in-ccli"></a>方法: C++/CLI で列挙型を定義および使用する

このトピックでは、C++/CLI の列挙について説明します。

## <a name="specifying-the-underlying-type-of-an-enum"></a>列挙型の基になる型の指定

既定では、列挙体の基になる型は`int`です。  ただし`int`、 、 `short`、 、`long`または`__int32``__int64`の署名付きのフォームまたは符号なしのフォームの種類を指定できます。  `char` を使用することもできます。

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

## <a name="how-to-convert-between-managed-and-standard-enumerations"></a>マネージ列挙と標準列挙体の間で変換する方法

列挙型と整数型の間に標準変換はありません。キャストが必要です。

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

C++/CLI の列挙型では、次の演算子が有効です。

|演算子|
|--------------|
|== != \<  >  \<= >=|
|+ -|
|&#124; ^ & ~|
|++ --|
|sizeof|

^ & ~ ) &#124;演算子は、bool を含まない整数型の基底型の列挙体に対してのみ定義されます。  両方のオペランドは列挙型である必要があります。

コンパイラは、列挙演算の結果を静的または動的にチェックしません。操作の結果、列挙型の有効な列挙子の範囲外の値が返される場合があります。

> [!NOTE]
> C++11 では、C++/CLI のマネージ列挙型クラスとは大きく異なるアンマネージ コードで列挙型クラス型が導入されています。 特に、C++11 列挙型クラス型は C++/CLI のマネージ列挙型クラス型と同じ演算子をサポートしていないため、C++/CLI ソース コードは、アンマネージ (C++11) 列挙クラス宣言と区別するために、マネージ列挙型クラス宣言でアクセシビリティ指定子を提供する必要があります。 C++/CLI、C++/CX、およびC++11の列挙型クラスの詳細については、[列挙型クラス](../extensions/enum-class-cpp-component-extensions.md)を参照してください。

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
