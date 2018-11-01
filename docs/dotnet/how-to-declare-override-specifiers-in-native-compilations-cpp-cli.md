---
title: '方法: オーバーライド指定子を宣言 (C +/cli CLI)'
ms.date: 11/04/2016
helpviewer_keywords:
- override specifiers in native compilation, overriding
ms.assetid: d0551836-9ac7-41eb-a6e9-a4b3ef60767d
ms.openlocfilehash: a0c2d65aa44141b1dbe30fb39d66beabde93fa99
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50555546"
---
# <a name="how-to-declare-override-specifiers-in-native-compilations-ccli"></a>方法: ネイティブ コンパイルでオーバーライド指定子を宣言する (C++/CLI)

[封印された](../windows/sealed-cpp-component-extensions.md)、[抽象](../windows/abstract-cpp-component-extensions.md)、および[オーバーライド](../windows/override-cpp-component-extensions.md)は使用しないでコンパイルで使用可能な **/ZW**または[/clr](../build/reference/clr-common-language-runtime-compilation.md)します。

> [!NOTE]
>  ISO c 11 標準言語が、[オーバーライド](../cpp/override-specifier.md)識別子と[最終的な](../cpp/final-specifier.md)識別子、およびその両方が Visual Studio の使用でサポートされている`final`の代わりに`sealed`するものではコードで(ネイティブのみ) としてコンパイルします。

## <a name="example"></a>例

### <a name="description"></a>説明

例を次に示します`sealed`はネイティブ コンパイルで有効です。

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

次の例を示します`override`はネイティブ コンパイルで有効です。

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

この例では`abstract`はネイティブ コンパイルで有効です。

### <a name="code"></a>コード

```cpp
// abstract_native_keyword.cpp
class X abstract {};

int main() {
   X * MyX = new X;   // C3622 cannot instantiate abstract class
}
```

## <a name="see-also"></a>関連項目

[オーバーライド指定子](../windows/override-specifiers-cpp-component-extensions.md)