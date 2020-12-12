---
description: '詳細情報: コンパイラの警告 (レベル 4) C4205'
title: コンパイラの警告 (レベル 4) C4205
ms.date: 11/04/2016
f1_keywords:
- C4205
helpviewer_keywords:
- C4205
ms.assetid: 39b5108c-7230-41b4-b2fe-2293eb6aae28
ms.openlocfilehash: d4a9250ad84f45a9e2ce40e6f103904ce7f8722e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97173234"
---
# <a name="compiler-warning-level-4-c4205"></a>コンパイラの警告 (レベル 4) C4205

非標準の拡張機能が使用されています: 関数スコープの静的関数宣言

Microsoft 拡張機能 (/Ze) では、 **`static`** 関数を別の関数内で宣言できます。 関数にはグローバルスコープが指定されています。

## <a name="example"></a>例

```c
// C4205.c
// compile with: /W4
void func1()
{
   static int func2();  // C4205
};

int main()
{
}
```

このような初期化は、ANSI 互換 ([/za](../../build/reference/za-ze-disable-language-extensions.md)) では無効です。
