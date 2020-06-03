---
title: 非推奨 (C++)
ms.date: 03/28/2017
f1_keywords:
- deprecated_cpp
helpviewer_keywords:
- __declspec keyword [C++], deprecated
- deprecated __declspec keyword
ms.assetid: beef1129-9434-4cb3-8392-f1eb29e04805
ms.openlocfilehash: e4689d3cb1a1757e2ac3bf4ca9eef7670ad5c655
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80189482"
---
# <a name="deprecated-c"></a>非推奨 (C++)

このトピックでは、Microsoft 固有の非推奨の declspec 宣言について説明します。 C++ 14 `[[deprecated]]` 属性、およびその属性を Microsoft 固有の declspec またはプラグマと共に使用する場合のガイダンスについては、「 [ C++標準属性](attributes.md)」を参照してください。

次に示す例外を使用して、**非**推奨の宣言は、[非推奨](../preprocessor/deprecated-c-cpp.md)のプラグマと同じ機能を提供します。

- **非推奨**の宣言を使用すると、関数オーバーロードの特定の形式を非推奨として指定できます。一方、プラグマフォームは、関数名のすべてのオーバーロードされた形式に適用されます。

- **非推奨**の宣言を使用すると、コンパイル時に表示されるメッセージを指定できます。 このメッセージのテキストをマクロから取り込むことができます。

- マクロは、**非**推奨のプラグマでのみ非推奨としてマークできます。

コンパイラが非推奨の識別子または標準の[`[[deprecated]]`](attributes.md)属性の使用を検出すると、 [C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md)警告がスローされます。

## <a name="example"></a>例

次の例では、関数を非推奨としてマークする方法、および非推奨の関数が使用されている場合、コンパイル時に表示されるメッセージを指定する方法を示します。

```cpp
// deprecated.cpp
// compile with: /W3
#define MY_TEXT "function is deprecated"
void func1(void) {}
__declspec(deprecated) void func1(int) {}
__declspec(deprecated("** this is a deprecated function **")) void func2(int) {}
__declspec(deprecated(MY_TEXT)) void func3(int) {}

int main() {
   func1();
   func1(1);   // C4996
   func2(1);   // C4996
   func3(1);   // C4996
}
```

## <a name="example"></a>例

次の例では、クラスを非推奨としてマークする方法、および非推奨のクラスが使用されている場合、コンパイル時に表示されるメッセージを指定する方法を示します。

```cpp
// deprecate_class.cpp
// compile with: /W3
struct __declspec(deprecated) X {
   void f(){}
};

struct __declspec(deprecated("** X2 is deprecated **")) X2 {
   void f(){}
};

int main() {
   X x;   // C4996
   X2 x2;   // C4996
}
```

## <a name="see-also"></a>参照

[__declspec](../cpp/declspec.md)<br/>
[キーワード](../cpp/keywords-cpp.md)
