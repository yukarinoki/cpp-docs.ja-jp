---
title: コンパイラの警告 C4693
ms.date: 10/25/2017
f1_keywords:
- C4693
helpviewer_keywords:
- C4693
ms.assetid: 72d8db01-5e6f-4794-8731-76107e8f064a
ms.openlocfilehash: cac5918eb4a1689fd215e07272958eeca48247ad
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59779441"
---
# <a name="compiler-warning-c4693"></a>コンパイラの警告 C4693

> 'class': シールされた抽象クラスにインスタンス メンバー 'Test' を含めることはできません

型がマークされている場合[シール](../../extensions/sealed-cpp-component-extensions.md)と[抽象](../../extensions/abstract-cpp-component-extensions.md)、静的メンバーをのみがあることができます。

この警告は、自動的にエラーになります。 この動作を変更する場合を使用して、 [#pragma warning](../../preprocessor/warning.md)します。

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