---
title: マネージ、アンマネージ |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- vc-pragma.unmanaged
- managed_CPP
- unmanaged_CPP
- vc-pragma.managed
dev_langs:
- C++
helpviewer_keywords:
- managed pragma
- pragmas, unmanaged
- pragmas, managed
- unmanaged pragma
ms.assetid: f072ddcc-e1ec-408a-8ce1-326ddb60e4a4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2fdfcf65280f3be639da8f6e49f3d93a498478dd
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50070882"
---
# <a name="managed-unmanaged"></a>マネージド、アンマネージド
関数をマネージドまたはアンマネージドとしてコンパイルするために関数レベルの制御を有効にします。

## <a name="syntax"></a>構文

```
#pragma managed
#pragma unmanaged
#pragma managed([push,] on | off)
#pragma managed(pop)
```

## <a name="remarks"></a>Remarks

[/Clr](../build/reference/clr-common-language-runtime-compilation.md)コンパイラ オプションは、関数をマネージまたはアンマネージとしてコンパイルのモジュール レベルの制御を提供します。

アンマネージ関数は、ネイティブ プラットフォーム用にコンパイルされ、プログラムのその部分の実行は、共通言語ランタイムによってネイティブ プラットフォームに渡されます。

関数は、`/clr` が使用されると、既定でマネージとしてコンパイルされます。

これらのプラグマを適用するときは次のようにします。

- 関数の前にあり関数本体内にはないプラグマを追加します。

- `#include` ステートメントの後にプラグマを追加します。 `#include` ステートメントの前でこれらのプラグマを使用しないでください。

コンパイラは無視、**マネージ**と**アンマネージ**プラグマ場合`/clr`コンパイルでは使用されません。

テンプレート関数がインスタンス化されるとき、テンプレートの定義時のプラグマの状態により、マネージドかアンマネージドかが決まります。

詳細については、次を参照してください。[混在アセンブリの初期化](../dotnet/initialization-of-mixed-assemblies.md)します。

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

[プラグマ ディレクティブと __Pragma キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)