---
description: '詳細情報: 非推奨 (C++)'
title: 非推奨 (C++)
ms.date: 03/28/2017
f1_keywords:
- deprecated_cpp
helpviewer_keywords:
- __declspec keyword [C++], deprecated
- deprecated __declspec keyword
ms.assetid: beef1129-9434-4cb3-8392-f1eb29e04805
ms.openlocfilehash: cd7bc3acbe6a61e87a1766025bcc174268190c48
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97339424"
---
# <a name="deprecated-c"></a>非推奨 (C++)

このトピックでは、Microsoft 固有の非推奨の declspec 宣言について説明します。 C++ 14 属性に関する情報 `[[deprecated]]` と、その属性を使用するタイミングと Microsoft 固有の declspec またはプラグマに関するガイダンスについては、「 [C++ 標準属性](attributes.md)」を参照してください。

次に示す例外では、 **`deprecated`** [非推奨](../preprocessor/deprecated-c-cpp.md) のプラグマと同じ機能が宣言に用意されています。

- **`deprecated`** 宣言を使用すると、関数オーバーロードの特定の形式を非推奨として指定できます。一方、プラグマフォームは、関数名のすべてのオーバーロードされた形式に適用されます。

- **`deprecated`** 宣言を使用すると、コンパイル時に表示されるメッセージを指定できます。 このメッセージのテキストをマクロから取り込むことができます。

- マクロは、プラグマで非推奨としてのみマークでき **`deprecated`** ます。

コンパイラが非推奨の識別子または標準属性の使用を検出すると [`[[deprecated]]`](attributes.md) 、 [C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md) 警告がスローされます。

## <a name="examples"></a>例

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

## <a name="see-also"></a>関連項目

[__declspec](../cpp/declspec.md)<br/>
[キーワード](../cpp/keywords-cpp.md)
