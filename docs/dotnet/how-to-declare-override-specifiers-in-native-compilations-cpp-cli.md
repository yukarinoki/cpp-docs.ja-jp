---
title: '方法: オーバーライド指定子を宣言する (C++/CLI)'
ms.date: 11/04/2016
helpviewer_keywords:
- override specifiers in native compilation, overriding
ms.assetid: d0551836-9ac7-41eb-a6e9-a4b3ef60767d
ms.openlocfilehash: c5ed413f403fb12f116633c0e39f9e7b32b2e9f8
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87221329"
---
# <a name="how-to-declare-override-specifiers-in-native-compilations-ccli"></a>方法: ネイティブ コンパイルでオーバーライド指定子を宣言する (C++/CLI)

[sealed](../extensions/sealed-cpp-component-extensions.md)、 [abstract](../extensions/abstract-cpp-component-extensions.md)、および[override](../extensions/override-cpp-component-extensions.md)は、 **/ZW**または[/clr](../build/reference/clr-common-language-runtime-compilation.md)を使用しないコンパイルで使用できます。

> [!NOTE]
> ISO C++ 11 標準言語には、[オーバーライド](../cpp/override-specifier.md)識別子と[最後](../cpp/final-specifier.md)の識別子があり、どちらも `final` **`sealed`** ネイティブ専用としてコンパイルされるコードではなく、Visual Studio の使用でサポートされています。

## <a name="example"></a>例

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

## <a name="example"></a>例

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

## <a name="example"></a>例

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
