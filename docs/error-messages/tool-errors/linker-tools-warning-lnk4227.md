---
title: リンカー ツールの警告 LNK4227
ms.date: 11/04/2016
f1_keywords:
- LNK4227
helpviewer_keywords:
- LNK4227
ms.assetid: 941a0414-9964-4e02-8487-f9daa42ef7f9
ms.openlocfilehash: 7ac3ef2b6ad8f05a454dafe5e6a7ea0abc07a066
ms.sourcegitcommit: c1fd917a8c06c6504f66f66315ff352d0c046700
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/16/2020
ms.locfileid: "90685490"
---
# <a name="linker-tools-warning-lnk4227"></a>リンカー ツールの警告 LNK4227

> メタデータ操作の警告 (*HRESULT*): *warning_message*

リンカーがマージ時にメタデータの相違点を検出しました:

- アセンブリが現在ビルドされている1つ以上の参照アセンブリ。

- コンパイル内の1つ以上のソースコードファイル。

たとえば、同じ名前の2つのグローバル関数があり、パラメーター情報が異なる方法で宣言されている (つまり、すべての compilands で宣言が一致しない) 場合、LNK4227 が発生する可能性があります。 各 .obj ファイルに対して ildasm.exe/TEXT/METADATA *object_file* を使用して、型がどのように異なるかを確認します。

LNK4227 は、別のツールで発生した問題を報告するためにも使用されます。 詳細については、警告メッセージを検索してください。

警告を解決するには、メタデータの問題を修正する必要があります。

## <a name="examples"></a>例

LNK4227 は、参照されたアセンブリがそれを参照するアセンブリとは異なる方法で署名された場合に生成されます。

次の例では、LNK4227 が生成されます。

```cpp
// LNK4227.cpp
// compile with: /clr
using namespace System::Reflection;

[assembly:AssemblyDelaySignAttribute(false)];

int main() {}
```

それから

```cpp
// LNK4227b.cpp
// compile with: /clr LNK4227.cpp /FeLNK4227b.exe
using namespace System::Reflection;
using namespace System::Runtime::CompilerServices;

[assembly:AssemblyDelaySignAttribute(true)];
// Try the following line instead
// [assembly:AssemblyDelaySignAttribute(false)];

ref class MyClass
{
};
```

LNK4227 は、間違った形式のバージョン番号がアセンブリ属性に渡された場合にも生成できます。  ' * ' 表記は、に固有です `AssemblyVersionAttribute` 。  この警告を解決するには、以外のバージョン属性の数値のみを使用 `AssemblyVersionAttribute` します。

次の例では、LNK4227 が生成されます。

```cpp
// LNK4227e.cpp
// compile with: /clr /LD /W1
using namespace System::Reflection;
[assembly:AssemblyVersionAttribute("2.3.*")];   // OK
[assembly:AssemblyFileVersionAttribute("2.3.*")];   // LNK4227
// try the following line instead
// [assembly:AssemblyFileVersionAttribute("2.3")];
```
