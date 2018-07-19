---
title: コンパイラの警告 C4693 |Microsoft ドキュメント
ms.date: 10/25/2017
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4693
dev_langs:
- C++
helpviewer_keywords:
- C4693
ms.assetid: 72d8db01-5e6f-4794-8731-76107e8f064a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f8230e60d65c80b4f839cc8a1c97ccc0c7b18086
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33273882"
---
# <a name="compiler-warning-c4693"></a>コンパイラの警告 C4693

> 'class': シールされた抽象クラスにインスタンス メンバー 'Test' を含めることはできません

型がマークされている場合[シール](../../windows/sealed-cpp-component-extensions.md)と[抽象](../../windows/abstract-cpp-component-extensions.md)、静的メンバーを持つことができますのみです。

この警告は、自動的にエラーになります。 この動作を変更する場合は、使用[#pragma 警告](../../preprocessor/warning.md)です。

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