---
title: コンパイラの警告 (レベル 4) C4202
ms.date: 11/04/2016
f1_keywords:
- C4202
helpviewer_keywords:
- C4202
ms.assetid: 253293aa-97a3-4878-a2e8-c6cc9e20b1cb
ms.openlocfilehash: 8a449ee7650196d34d30df646ebdc333c1333af2
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80161427"
---
# <a name="compiler-warning-level-4-c4202"></a>コンパイラの警告 (レベル 4) C4202

非標準の拡張機能が使用されています: '... ': プロトタイプのパラメーター名の一覧が正しくありません。

旧形式の関数定義には、可変個の引数が含まれています。 これらの定義は、ANSI 互換 ([/za](../../build/reference/za-ze-disable-language-extensions.md)) でエラーを生成します。

## <a name="example"></a>例

```c
// C4202.c
// compile with: /W4
void func( a, b, ...)   // C4202
int a, b;
{}

int main()
{
}
```
