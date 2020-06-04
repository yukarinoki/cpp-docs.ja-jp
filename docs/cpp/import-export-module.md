---
title: モジュール、インポート、エクスポート
ms.date: 12/12/2019
f1_keywords:
- module_cpp
- import_cpp
- export_cpp
helpviewer_keywords:
- modules [C++]
- modules [C++], import
- modules [C++], export
description: 指定したモジュールで定義されている型と関数にアクセスし、公開するには、インポート宣言とエクスポート宣言を使用します。
ms.openlocfilehash: a765e9a406660d3c945ef3d70754178b0648458c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374109"
---
# <a name="module-import-export"></a>モジュール、インポート、エクスポート

**モジュール**、**インポート**、および**エクスポート**の各宣言は C++20 で使用でき[、/実験:モジュール](../build/reference/experimental-module.md)コンパイラ スイッチと[/std:c++ の最新](../build/reference/std-specify-language-standard-version.md)のスイッチが必要です。 詳細については、「 [C++ モジュールの概要](modules-cpp.md)」を参照してください。

## <a name="module"></a>name

モジュール実装ファイルの先頭に**モジュール**宣言を配置して、ファイルの内容が名前付きモジュールに属することを指定します。

```cpp
module ModuleA;
```

## <a name="export"></a>エクスポート

モジュールのプライマリ インターフェイス ファイルには **、拡張子** **.ixx**を持つエクスポート モジュール宣言を使用します。

```cpp
export module ModuleA;
```

インターフェイス ファイルで、パブリック インターフェイスの一部として使用する名前に対して**export**修飾子を使用します。

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

エクスポートされていない名前は、モジュールをインポートするコードには表示されません。

```cpp
//MyProgram.cpp

import module ModuleA;

int main() {
  Bar::f(); // OK
  Bar::d(); // OK
  Bar::internal_f(); // Ill-formed: error C2065: 'internal_f': undeclared identifier
}
```

モジュール実装ファイルに**export**キーワードが含まれていない場合があります。 名前空間名に**エクスポート**を適用すると、名前空間内のすべての名前がエクスポートされます。

## <a name="import"></a>import

**インポート**宣言を使用して、モジュールの名前をプログラム内で表示できます。 import 宣言は、モジュール宣言の後、および#includeディレクティブの後、ファイル内の宣言の前に記述する必要があります。

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

## <a name="remarks"></a>解説

**インポート**と**モジュール**の両方がキーワードとして扱われるのは、論理行の先頭に表示される場合のみです。

```cpp

// OK:
module ;
module module-name
import :
import <
import "
import module-name
export module ;
export module module-name
export import :
export import <
export import "
export import module-name

// Error:
int i; module ;
```

**マイクロソフト固有**

Microsoft C++ では、トークンの**インポート**と**モジュール**は常に識別子であり、マクロの引数として使用される場合はキーワードは使用しません。

### <a name="example"></a>例

```cpp
#define foo(…) __VA_ARGS__
foo(
import // Always an identifier, never a keyword
)
```

**END Microsoft 固有の仕様**

## <a name="see-also"></a>参照

[C++ のモジュールの概要](modules-cpp.md)
