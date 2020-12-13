---
description: 詳細については、「マネージ、アンマネージプラグマ」を参照してください。
title: マネージド、アンマネージド プラグマ
ms.date: 08/29/2019
f1_keywords:
- vc-pragma.unmanaged
- managed_CPP
- unmanaged_CPP
- vc-pragma.managed
helpviewer_keywords:
- managed pragma
- pragmas, unmanaged
- pragmas, managed
- unmanaged pragma
ms.assetid: f072ddcc-e1ec-408a-8ce1-326ddb60e4a4
ms.openlocfilehash: 10f632b009c9922f67f4321acc862142d895e7ae
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333388"
---
# <a name="managed-unmanaged-pragmas"></a>マネージド、アンマネージド プラグマ

関数レベルの制御を有効にして、関数をマネージまたはアンマネージとしてコンパイルします。

## <a name="syntax"></a>構文

> **マネージド #pragma**\
> **アンマネージ #pragma**\
> **#pragma 管理 (** [**プッシュ,** ] { **on**  |  **off** } **)**\
> **#pragma マネージ (pop)**

## <a name="remarks"></a>解説

[/Clr](../build/reference/clr-common-language-runtime-compilation.md)コンパイラオプションは、関数をマネージまたはアンマネージとしてコンパイルするためのモジュールレベルのコントロールを提供します。

アンマネージ関数は、ネイティブプラットフォーム用にコンパイルされます。 プログラムのその部分の実行は、共通言語ランタイムによってネイティブプラットフォームに渡されます。

関数は、`/clr` が使用されると、既定でマネージドとしてコンパイルされます。

これらのプラグマを適用するときは次のようにします。

- 関数の前にプラグマを追加しますが、関数本体内には追加しません。

- `#include` ステートメントの後にプラグマを追加します。 ステートメントの前にこれらのプラグマを使用しないで `#include` ください。

コンパイルでが使用されていない場合、コンパイラは **マネージ** プラグマおよび **アンマネージ** プラグマを無視し `/clr` ます。

テンプレート関数がインスタンス化されると、テンプレートが定義されているときのプラグマの状態によって、マネージとアンマネージのどちらであるかが決まります。

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

[プラグマ ディレクティブと __pragma キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
