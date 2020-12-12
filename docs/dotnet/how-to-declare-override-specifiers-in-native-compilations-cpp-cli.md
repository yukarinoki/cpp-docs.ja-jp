---
description: '詳細については、「方法: ネイティブコンパイルでオーバーライド指定子を宣言する (C++/CLI)」を参照してください。'
title: '方法: オーバーライド指定子を宣言する (C++/CLI)'
ms.date: 11/04/2016
helpviewer_keywords:
- override specifiers in native compilation, overriding
ms.assetid: d0551836-9ac7-41eb-a6e9-a4b3ef60767d
ms.openlocfilehash: 75e925e26dc62d87e40d56b05e3be6d2dbda3e4a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97246397"
---
# <a name="how-to-declare-override-specifiers-in-native-compilations-ccli"></a>方法: ネイティブ コンパイルでオーバーライド指定子を宣言する (C++/CLI)

[sealed](../extensions/sealed-cpp-component-extensions.md)、 [abstract](../extensions/abstract-cpp-component-extensions.md)、および [override](../extensions/override-cpp-component-extensions.md) は、 **/ZW** または [/clr](../build/reference/clr-common-language-runtime-compilation.md)を使用しないコンパイルで使用できます。

> [!NOTE]
> ISO C++ 11 標準言語には、 [オーバーライド](../cpp/override-specifier.md) 識別子と [最後](../cpp/final-specifier.md) の識別子があり、どちらも `final` **`sealed`** ネイティブ専用としてコンパイルされるコードではなく、Visual Studio の使用でサポートされています。

## <a name="example-sealed-is-valid"></a>例: sealed は有効です

### <a name="description"></a>説明

次の例は、 **`sealed`** がネイティブコンパイルで有効であることを示しています。

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

## <a name="example-override-is-valid"></a>例: オーバーライドは有効です

### <a name="description"></a>説明

次の例は、 `override` がネイティブコンパイルで有効であることを示しています。

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

## <a name="example-abstract-is-valid"></a>例: abstract は有効です

### <a name="description"></a>説明

この例は、 **`abstract`** ネイティブコンパイルでが有効であることを示しています。

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
