---
description: '詳細情報: __identifier (C++/CLI)'
title: __identifier (C++/CLI)
ms.date: 10/12/2018
ms.topic: reference
f1_keywords:
- __identifier
- __identifier_cpp
helpviewer_keywords:
- __identifier keyword [C++]
ms.assetid: 348428af-afa7-4ff3-b571-acf874301cf2
ms.openlocfilehash: 663d05ef482a97b4ac33664ab62f1556e62763a6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97119097"
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

### <a name="requirements"></a>要件

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

### <a name="requirements"></a>要件

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
