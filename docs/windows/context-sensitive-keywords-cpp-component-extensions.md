---
title: 状況依存のキーワード (C +/cli および C++/cli CX)
ms.date: 10/12/2018
ms.topic: reference
f1_keywords:
- internal_CPP
helpviewer_keywords:
- context-sensitive keywords
ms.assetid: e33da089-f434-44e9-8cce-4668d05a8939
ms.openlocfilehash: 78b61e77da8ed45a43b3830b7eaa9588c1860928
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50652752"
---
# <a name="context-sensitive-keywords--ccli-and-ccx"></a>状況依存のキーワード (C +/cli および C++/cli CX)

*状況依存のキーワード*は特定のコンテキストでのみ認識される言語要素です。 特定のコンテキスト以外では、状況依存のキーワードをユーザー定義の記号として使用することができます。

## <a name="all-runtimes"></a>すべてのランタイム

### <a name="remarks"></a>Remarks

以下は、状況依存のキーワードの一覧です。

- [abstract](../windows/abstract-cpp-component-extensions.md)

- [delegate](../windows/delegate-cpp-component-extensions.md)

- [event](../windows/event-cpp-component-extensions.md)

- [finally](../dotnet/finally.md)

- [for each、in](../dotnet/for-each-in.md)

- [initonly](../dotnet/initonly-cpp-cli.md)

- `internal`

- [name](../windows/literal-cpp-component-extensions.md)

- [override](../windows/override-cpp-component-extensions.md)

- [プロパティ](../windows/property-cpp-component-extensions.md)

- [sealed](../windows/sealed-cpp-component-extensions.md)

- `where` (一部の[ジェネリック](../windows/generics-cpp-component-extensions.md))

読みやすさのために、ユーザー定義シンボルとしての状況依存のキーワードの使用を制限します。

## <a name="windows-runtime"></a>Windows ランタイム

### <a name="remarks"></a>Remarks

(この機能のプラットフォーム固有の解説はありません。)

### <a name="requirements"></a>必要条件

コンパイラ オプション: `/ZW`

## <a name="common-language-runtime"></a>共通言語ランタイム

### <a name="remarks"></a>Remarks

(この機能のプラットフォーム固有の解説はありません。)

### <a name="requirements"></a>必要条件

コンパイラ オプション: `/clr`

### <a name="examples"></a>使用例

適切なコンテキストでのコード例を次に示します、**プロパティ**状況依存のキーワードは、プロパティと変数を定義するために使用できます。

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

## <a name="see-also"></a>関連項目

[Component Extensions for .NET と UWP](../windows/component-extensions-for-runtime-platforms.md)