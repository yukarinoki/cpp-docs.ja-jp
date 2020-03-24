---
title: コンパイラの警告 C4693
ms.date: 10/25/2017
f1_keywords:
- C4693
helpviewer_keywords:
- C4693
ms.assetid: 72d8db01-5e6f-4794-8731-76107e8f064a
ms.openlocfilehash: 71c3db18b400ce94bff3c643d6728a6613061039
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80165133"
---
# <a name="compiler-warning-c4693"></a>コンパイラの警告 C4693

> 'class': シールされた抽象クラスにインスタンス メンバー 'Test' を含めることはできません

型が[sealed](../../extensions/sealed-cpp-component-extensions.md)および[abstract](../../extensions/abstract-cpp-component-extensions.md)としてマークされている場合は、静的メンバーのみを持つことができます。

この警告は、自動的にエラーになります。 この動作を変更する場合は、 [#pragma 警告](../../preprocessor/warning.md)を使用します。

## <a name="example"></a>例

次の例では C4693 警告が生成されます。

```cpp
// C4693.cpp
// compile with: /clr /c
public ref class Public_Ref_Class sealed abstract {
public:
   void Test() {}   // C4693
   static void Test2() {}   // OK
};
```
