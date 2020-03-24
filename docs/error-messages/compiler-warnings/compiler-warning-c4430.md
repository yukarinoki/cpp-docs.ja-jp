---
title: コンパイラの警告 C4430
ms.date: 11/04/2016
f1_keywords:
- C4430
helpviewer_keywords:
- C4430
ms.assetid: 12efbfff-aa58-4a86-a7d6-2c6a12d01dd3
ms.openlocfilehash: 091d988a5af277e78a2954eb5b0b95bc64c56069
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80165263"
---
# <a name="compiler-warning-c4430"></a>コンパイラの警告 C4430

型指定子がありません - int と仮定しました。 注: C++では、既定の-int はサポートされていません。

このエラーは、Visual Studio 2005 で実行されたコンパイラ準拠作業の結果として生成される場合があります。すべての宣言で型を明示的に指定する必要があります。int は想定されなくなりました。

C4430 は常にエラーとして発行されます。  この警告は、`#pragma warning` または **/wd**で無効にすることができます。詳細については、「 [warning](../../preprocessor/warning.md)または[/w、/W0、/W1、/W2、/W3、/W4、/W1、/W2、](../../build/reference/compiler-option-warning-level.md) /W3、/W4、/Wall、/wd、/we、/WO、/Wv、/wx (警告レベル)」を参照してください。

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
