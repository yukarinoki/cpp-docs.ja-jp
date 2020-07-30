---
title: C スタイル キャストと -clr (C++/CLI)
ms.date: 10/12/2018
ms.topic: reference
helpviewer_keywords:
- C-style casts and /clr
ms.assetid: d2a4401a-156a-4da9-8d12-923743e26913
ms.openlocfilehash: daaf92e36550c5479903dec4869b1cb116c0a65a
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87219795"
---
# <a name="c-style-casts-with-clr-ccli"></a>C スタイル キャストと /clr (C++/CLI)

次のトピックは、共通言語ランタイムのみに適用されます。

CLR 型で使用すると、コンパイラは、C スタイルのキャストを次のいずれかのキャストに、次の順序でマップしようとします。

1. const_cast

2. safe_cast

3. safe_cast plus const_cast

4. static_cast

5. static_cast plus const_cast

上記のキャストのいずれも有効でない場合、または式の型とターゲットの型が CLR 参照型の場合、 C スタイルのキャストはランタイム チェックにマップされます (castclass MSIL 命令)。 それ以外の場合、C スタイルのキャストは無効とみなされ、コンパイラでエラーが発行されます。

## <a name="remarks"></a>解説

C スタイルのキャストは推奨されません。 [/clr (共通言語ランタイムのコンパイル)](../build/reference/clr-common-language-runtime-compilation.md) でコンパイルするときは、[safe_cast](safe-cast-cpp-component-extensions.md) を使用してください。

次のサンプルは、にマップされる C スタイルのキャストを示して **`const_cast`** います。

```cpp
// cstyle_casts_1.cpp
// compile with: /clr
using namespace System;

ref struct R {};
int main() {
   const R^ constrefR = gcnew R();
   R^ nonconstR = (R^)(constrefR);
}
```

次の例では、**safe_cast** にマップされる C スタイルのキャストを示します。

```cpp
// cstyle_casts_2.cpp
// compile with: /clr
using namespace System;
int main() {
   Object ^ o = "hello";
   String ^ s = (String^)o;
}
```

次のサンプルは、 **safe_cast**プラスにマップされる C スタイルのキャストを示して **`const_cast`** います。

```cpp
// cstyle_casts_3.cpp
// compile with: /clr
using namespace System;

ref struct R {};
ref struct R2 : public R {};

int main() {
   const R^ constR2 = gcnew R2();
   try {
   R2^ b2DR = (R2^)(constR2);
   }
   catch(InvalidCastException^ e) {
      System::Console::WriteLine("Invalid Exception");
   }
}
```

次のサンプルは、にマップされる C スタイルのキャストを示して **`static_cast`** います。

```cpp
// cstyle_casts_4.cpp
// compile with: /clr
using namespace System;

struct N1 {};
struct N2 {
   operator N1() {
      return N1();
   }
};

int main() {
   N2 n2;
   N1 n1 ;
   n1 = (N1)n2;
}
```

次のサンプルは、+ にマップされる C スタイルのキャストを示して **`static_cast`** **`const_cast`** います。

```cpp
// cstyle_casts_5.cpp
// compile with: /clr
using namespace System;
struct N1 {};

struct N2 {
   operator const N1*() {
      static const N1 n1;
      return &n1;
   }
};

int main() {
   N2 n2;
   N1* n1 = (N1*)(const N1*)n2;   // const_cast + static_cast
}
```

次の例では、ランタイム チェックにマップされる C スタイルのキャストを示します。

```cpp
// cstyle_casts_6.cpp
// compile with: /clr
using namespace System;

ref class R1 {};
ref class R2 {};

int main() {
   R1^ r  = gcnew R1();
   try {
      R2^ rr = ( R2^)(r);
   }
   catch(System::InvalidCastException^ e) {
      Console::WriteLine("Caught expected exception");
   }
}
```

次の例では、コンパイラでエラーが発行される無効な C スタイルのキャストを示します。

```cpp
// cstyle_casts_7.cpp
// compile with: /clr
using namespace System;
int main() {
   String^s = S"hello";
   int i = (int)s;   // C2440
}
```

## <a name="requirements"></a>必要条件

コンパイラ オプション: `/clr`

## <a name="see-also"></a>関連項目

[.NET および UWP 用のコンポーネントの拡張機能](component-extensions-for-runtime-platforms.md)
