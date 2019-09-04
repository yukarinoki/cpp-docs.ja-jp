---
title: モジュール、インポート、エクスポート
ms.date: 07/15/2019
f1_keywords:
- module_cpp
- import_cpp
- export_cpp
helpviewer_keywords:
- modules [C++]
- modules [C++], import
- modules [C++], export
description: 指定されたモジュールで定義されている型および関数にアクセスするには、import ステートメントを使用します。
ms.openlocfilehash: ee1d50a76a3304359c0771aa0174968439f5faa4
ms.sourcegitcommit: fd0f8839da5c6a3663798a47c6b0bb6e63b518bd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2019
ms.locfileid: "70273622"
---
# <a name="module-import-export"></a>モジュール、インポート、エクスポート

**Module**、 **import**、および**export**キーワードは c++ 20 で使用でき、/[実験的: モジュール](../build/reference/experimental-module.md)コンパイラスイッチと共に、 [/std: C + + latest](../build/reference/std-specify-language-standard-version.md)が必要です。 詳細については、「」の「 [ C++モジュールの概要](modules-cpp.md)」を参照してください。

## <a name="module"></a>name

モジュール実装ファイルの先頭にある**module**ステートメントを使用して、ファイルの内容が名前付きモジュールに属していることを指定します。 

```cpp
module ModuleA;
```

## <a name="export"></a>export

モジュールのプライマリインターフェイスファイルの**export モジュール**ステートメントを使用します。このファイルには拡張子を指定する必要があり**ます。 ixx**:

```cpp
export module ModuleA;
```

インターフェイスファイルでは、パブリックインターフェイスの一部として意図されている名前に対して**export**修飾子を使用します。

```cpp
// ModuleA.ixx

export module ModuleA;

namespace Bar
{
   export int f();
   export double d();
   double internal_f(); // not exported
}
```

エクスポートされていない名前は、モジュールをインポートするコードからは参照できません。

```cpp
//MyProgram.cpp

import module ModuleA;

void main() {
  Bar::f(); // OK
  Bar::d(); // OK
  Bar::internal_f(); // Ill-formed: error C2065: 'internal_f': undeclared identifier
}
```

**Export**キーワードは、モジュール実装ファイルには記述できません。 **エクスポート**修飾子が名前空間名に適用されると、名前空間内のすべての名前がエクスポートされます。

## <a name="import"></a>import

モジュールの名前がプログラムに表示されるようにするには、 **import**ステートメントを使用します。 Import ステートメントは、モジュールステートメントの後、任意の #include ディレクティブの後、ファイル内の宣言の前に記述する必要があります。

```cpp
module ModuleA;

#include "custom-lib.h"
import std.core;
import std.regex;
import ModuleB;

// begin declarations here:
template <class T>
class Baz
{...};
```

## <a name="see-also"></a>関連項目

[のモジュールの概要C++](modules-cpp.md)
