---
title: __identifier (C++/CLI)
ms.date: 10/12/2018
ms.topic: reference
f1_keywords:
- __identifier
- __identifier_cpp
helpviewer_keywords:
- __identifier keyword [C++]
ms.assetid: 348428af-afa7-4ff3-b571-acf874301cf2
ms.openlocfilehash: 5f95e9fc55acd33705b855c7c4f0ef268d4776a0
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87219691"
---
# <a name="__identifier-ccli"></a>__identifier (C++/CLI)

C++ キーワードを識別子として使用できるようにします。

## <a name="all-platforms"></a>すべてのプラットフォーム

### <a name="syntax"></a>構文

```cpp
__identifier(C++_keyword)
```

### <a name="remarks"></a>解説

キーワードではない識別子での **__identifier** キーワードの使用は許可されていますが、スタイルの問題として、極力回避することをお勧めします。

## <a name="windows-runtime"></a>Windows ランタイム

### <a name="requirements"></a>必要条件

コンパイラ オプション: `/ZW`

### <a name="examples"></a>例

**例**

次の例では、という名前のクラス `template` が C# で作成され、DLL として配布されます。 クラスを使用する C++/CLI プログラムで `template` は、キーワードは、 **`__identifier`** 標準 c++ キーワードであるファクトを隠し `template` ます。

```csharp
// identifier_template.cs
// compile with: /target:library
public class template {
   public void Run() { }
}
```

```cpp
// keyword__identifier.cpp
// compile with: /ZW
#using <identifier_template.dll>
int main() {
   __identifier(template)^ pTemplate = ref new __identifier(template)();
   pTemplate->Run();
}
```

## <a name="common-language-runtime"></a>共通言語ランタイム

### <a name="remarks"></a>解説

**__identifier** キーワードは、`/clr` コンパイラ オプションで有効です。

### <a name="requirements"></a>必要条件

コンパイラ オプション: `/clr`

### <a name="examples"></a>例

次の例では、という名前のクラス `template` が C# で作成され、DLL として配布されます。 クラスを使用する C++/CLI プログラムで `template` は、キーワードは、 **`__identifier`** 標準 c++ キーワードであるファクトを隠し `template` ます。

```csharp
// identifier_template.cs
// compile with: /target:library
public class template {
   public void Run() { }
}
```

```cpp
// keyword__identifier.cpp
// compile with: /clr
#using <identifier_template.dll>

int main() {
   __identifier(template) ^pTemplate = gcnew __identifier(template)();
   pTemplate->Run();
}
```

## <a name="see-also"></a>関連項目

[.NET および UWP 用のコンポーネントの拡張機能](component-extensions-for-runtime-platforms.md)<br/>
[.NET および UWP 用のコンポーネントの拡張機能](component-extensions-for-runtime-platforms.md)
