---
title: '方法 : オーバーライド指定子を宣言する (C++/CLI)'
ms.date: 11/04/2016
helpviewer_keywords:
- override specifiers in native compilation, overriding
ms.assetid: d0551836-9ac7-41eb-a6e9-a4b3ef60767d
ms.openlocfilehash: 9f3f6855f257d0af250b9bbdd2c0360b308ce775
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374451"
---
# <a name="how-to-declare-override-specifiers-in-native-compilations-ccli"></a>方法: ネイティブ コンパイルでオーバーライド指定子を宣言する (C++/CLI)

[/ZW](../extensions/sealed-cpp-component-extensions.md)または[/clr](../build/reference/clr-common-language-runtime-compilation.md)を使用しないコンパイルでは、**/ZW**シール 、[抽象](../extensions/abstract-cpp-component-extensions.md)、[およびオーバーライド](../extensions/override-cpp-component-extensions.md)を使用できます。

> [!NOTE]
> ISO C++11 標準言語には[オーバーライド](../cpp/override-specifier.md)識別子と[最終](../cpp/final-specifier.md)識別子があり、どちらもネイティブ専用としてコンパイルされるコードではなく`final`、Visual `sealed` Studio の使用でサポートされています。

## <a name="example"></a>例

### <a name="description"></a>説明

ネイティブ コンパイルで有効`sealed`な例を次に示します。

### <a name="code"></a>コード

```cpp
// sealed_native_keyword.cpp
#include <stdio.h>
__interface I1 {
   virtual void f();
   virtual void g();
};

class X : public I1 {
public:
   virtual void g() sealed {}
};

class Y : public X {
public:

   // the following override generates a compiler error
   virtual void g() {}   // C3248 X::g is sealed!
};
```

## <a name="example"></a>例

### <a name="description"></a>説明

次の例は、`override`ネイティブ コンパイルで有効であることを示しています。

### <a name="code"></a>コード

```cpp
// override_native_keyword.cpp
#include <stdio.h>
__interface I1 {
   virtual void f();
};

class X : public I1 {
public:
   virtual void f() override {}   // OK
   virtual void g() override {}   // C3668 I1::g does not exist
};
```

## <a name="example"></a>例

### <a name="description"></a>説明

この例では、`abstract`ネイティブ コンパイルで有効であることを示します。

### <a name="code"></a>コード

```cpp
// abstract_native_keyword.cpp
class X abstract {};

int main() {
   X * MyX = new X;   // C3622 cannot instantiate abstract class
}
```

## <a name="see-also"></a>関連項目

[オーバーライド指定子](../extensions/override-specifiers-cpp-component-extensions.md)
