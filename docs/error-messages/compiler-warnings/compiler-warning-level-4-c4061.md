---
title: コンパイラの警告 (レベル 4) C4061 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/30/2017
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4061
dev_langs:
- C++
helpviewer_keywords:
- C4061
ms.assetid: a99cf88e-7941-4519-8b1b-f6889d914b2f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2d0086ea5e590c7183024bc4dcc93e2f2522f483
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-4-c4061"></a>コンパイラの警告 (レベル 4) C4061

> 列挙子 '*識別子*'in 'の switch の*列挙*' は case ラベルによって明示的にハンドルされません

列挙子関連付けられたハンドラーがない、`switch`ステートメントです。

既定では、この警告はオフに設定されています。 詳細については、「 [既定で無効になっているコンパイラ警告](../../preprocessor/compiler-warnings-that-are-off-by-default.md) 」を参照してください。

## <a name="example"></a>例

次の例には、C4061; が生成されます。不足している列挙子を解決するためのケースを追加します。

```cpp
// C4061.cpp
// compile with: /W4
#pragma warning(default : 4061)

enum E { a, b, c };
void func ( E e )
{
   switch(e)
   {
      case a:
      case b:
      default:
         break;
   }   // C4061 c' not handled
}

int main()
{
}
```