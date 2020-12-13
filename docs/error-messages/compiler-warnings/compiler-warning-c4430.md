---
description: 詳細については、「コンパイラの警告 C4430」を参照してください。
title: コンパイラの警告 C4430
ms.date: 11/04/2016
f1_keywords:
- C4430
helpviewer_keywords:
- C4430
ms.assetid: 12efbfff-aa58-4a86-a7d6-2c6a12d01dd3
ms.openlocfilehash: af214bb0e9d373ee319008f509ba78f5d7ade38b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97344303"
---
# <a name="compiler-warning-c4430"></a>コンパイラの警告 C4430

型指定子がありません - int と仮定しました。 注: C++ では既定の-int はサポートされていません

このエラーは、Visual Studio 2005 で実行されたコンパイラ準拠作業の結果として生成される場合があります。すべての宣言で型を明示的に指定する必要があります。int は想定されなくなりました。

C4430 は常にエラーとして発行されます。  この警告は、または/wd で無効にできます `#pragma warning` 。詳細については、「 [warning](../../preprocessor/warning.md)または [/W、/W0、/W1、/W2、/W3、/W4、/W1、/W2、/W3、/W4、/Wall、/wd、/WE、/Wo、/Wv、/wx (警告レベル)](../../build/reference/compiler-option-warning-level.md) 」を参照してください。

## <a name="example"></a>例

次の例では、C4430 が生成されます。

```cpp
// C4430.cpp
// compile with: /c
struct CMyClass {
   CUndeclared m_myClass;  // C4430
   int m_myClass;  // OK
};

typedef struct {
   POINT();   // C4430
   // try the following line instead
   // int POINT();
   unsigned x;
   unsigned y;
} POINT;
```
