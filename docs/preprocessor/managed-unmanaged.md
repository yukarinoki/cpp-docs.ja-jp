---
description: pragmaMicrosoft C++ でのマネージディレクティブとアンマネージディレクティブの詳細について説明します。
title: マネージとアンマネージ pragma
ms.date: 01/22/2021
f1_keywords:
- vc-pragma.unmanaged
- managed_CPP
- unmanaged_CPP
- vc-pragma.managed
helpviewer_keywords:
- managed pragma
- pragma, unmanaged
- pragma, managed
- unmanaged pragma
no-loc:
- pragma
ms.openlocfilehash: a106e9a1370daeedb94bbf5e4d092ae85457a3d2
ms.sourcegitcommit: a26a66a3cf479e0e827d549a9b850fad99b108d1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "98713507"
---
# <a name="managed-and-unmanaged-no-locpragma"></a>`managed` および `unmanaged` pragma

関数レベルの制御を有効にして、関数をマネージまたはアンマネージとしてコンパイルします。

## <a name="syntax"></a>構文

> **`#pragma managed`**\
> **`#pragma unmanaged`**\
> **`#pragma managed(`** [ **`push,`** ] { **`on`** | **`off`** } **`)`**\
> **`#pragma managed(pop)`**

## <a name="remarks"></a>解説

[`/clr`](../build/reference/clr-common-language-runtime-compilation.md)コンパイラオプションは、関数をマネージまたはアンマネージとしてコンパイルするためのモジュールレベルのコントロールを提供します。

アンマネージ関数は、ネイティブプラットフォーム用にコンパイルされます。 プログラムのその部分の実行は、共通言語ランタイムによってネイティブプラットフォームに渡されます。

関数は、が使用されると、既定でマネージとしてコンパイルされ **`/clr`** ます。

またはを適用する場合 **`managed`** **`unmanaged`** pragma :

- 関数 pragma 本体内ではなく、関数の前に関数を追加します。

- After ステートメントを追加し pragma `#include` ます。 ステートメントの前に使用しないで `#include` ください。

**`managed`** **`unmanaged`** pragma コンパイルでが使用されていない場合、コンパイラはを無視し **`/clr`** ます。

テンプレート関数がインスタンス化されると、テンプレートが定義されているときの状態によって、管理されているかどうかが pragma 決まります。

詳細については、「 [混在アセンブリの初期化](../dotnet/initialization-of-mixed-assemblies.md)」を参照してください。

## <a name="example"></a>例

```cpp
// pragma_directives_managed_unmanaged.cpp
// compile with: /clr
#include <stdio.h>

// func1 is managed
void func1() {
   System::Console::WriteLine("In managed function.");
}

// #pragma unmanaged
// push managed state on to stack and set unmanaged state
#pragma managed(push, off)

// func2 is unmanaged
void func2() {
   printf("In unmanaged function.\n");
}

// #pragma managed
#pragma managed(pop)

// main is managed
int main() {
   func1();
   func2();
}
```

```Output
In managed function.
In unmanaged function.
```

## <a name="see-also"></a>関連項目

[プラグマディレクティブと `__pragma` `_Pragma` キーワードおよびキーワード](./pragma-directives-and-the-pragma-keyword.md)
