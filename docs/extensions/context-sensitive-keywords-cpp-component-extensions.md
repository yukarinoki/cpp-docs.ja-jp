---
title: 状況依存キーワード (C++/CLI および C++/CX)
ms.date: 10/12/2018
ms.topic: reference
f1_keywords:
- internal_CPP
helpviewer_keywords:
- context-sensitive keywords
ms.assetid: e33da089-f434-44e9-8cce-4668d05a8939
ms.openlocfilehash: 53fcaf13eb56ae14841861bffd1a29376304b8d6
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80182176"
---
# <a name="context-sensitive-keywords--ccli-and-ccx"></a>状況依存キーワード (C++/CLI および C++/CX)

*状況依存キーワード*は、特定のコンテキストでのみ認識される言語要素です。 特定のコンテキスト以外では、状況依存のキーワードをユーザー定義の記号として使用することができます。

## <a name="all-runtimes"></a>すべてのランタイム

### <a name="remarks"></a>解説

以下は、状況依存のキーワードの一覧です。

- [abstract](abstract-cpp-component-extensions.md)

- [delegate](delegate-cpp-component-extensions.md)

- [event](event-cpp-component-extensions.md)

- [finally](../dotnet/finally.md)

- [for each、in](../dotnet/for-each-in.md)

- [initonly](../dotnet/initonly-cpp-cli.md)

- `internal`

- [literal](literal-cpp-component-extensions.md)

- [override](override-cpp-component-extensions.md)

- [property](property-cpp-component-extensions.md)

- [sealed](sealed-cpp-component-extensions.md)

- `where` ([ジェネリック](generics-cpp-component-extensions.md)の一部)

読みやすくするために、状況依存キーワードの使用をユーザー定義記号に制限できます。

## <a name="windows-runtime"></a>Windows ランタイム

### <a name="remarks"></a>解説

(この機能のプラットフォーム固有の解説はありません。)

### <a name="requirements"></a>必要条件

コンパイラ オプション: `/ZW`

## <a name="common-language-runtime"></a>共通言語ランタイム

### <a name="remarks"></a>解説

(この機能のプラットフォーム固有の解説はありません。)

### <a name="requirements"></a>必要条件

コンパイラ オプション: `/clr`

### <a name="examples"></a>例

次のコード例では、適切なコンテキストで **property** 状況依存キーワードを使用して、プロパティと変数を定義できることを示します。

```cpp
// context_sensitive_keywords.cpp
// compile with: /clr
public ref class C {
   int MyInt;
public:
   C() : MyInt(99) {}

   property int Property_Block {   // context-sensitive keyword
      int get() { return MyInt; }
   }
};

int main() {
   int property = 0;               // variable name
   C ^ MyC = gcnew C();
   property = MyC->Property_Block;
   System::Console::WriteLine(++property);
}
```

```Output
100
```

## <a name="see-also"></a>参照

[.NET および UWP でのコンポーネント拡張](component-extensions-for-runtime-platforms.md)
