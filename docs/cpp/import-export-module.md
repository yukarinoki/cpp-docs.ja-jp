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
ms.openlocfilehash: fbb9c45ec816c859edb4df38ad67dc7778247e87
ms.sourcegitcommit: 7b039b5f32f6c59be6c6bb1cffafd69c3bfadd35
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/26/2019
ms.locfileid: "68537788"
---
# <a name="module-import-export"></a>モジュール、インポート、エクスポート

**Module**、 **import**、および**export**キーワードは`/experimental:modules` c++ 20 で使用でき、と共に`/std:c++latest`コンパイラスイッチが必要です。 詳細については、「」の「 [ C++モジュールの概要](modules-cpp.md)」を参照してください。

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
