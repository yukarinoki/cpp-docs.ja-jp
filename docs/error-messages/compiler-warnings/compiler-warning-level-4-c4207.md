---
title: コンパイラの警告 (レベル 4) C4207
ms.date: 11/04/2016
f1_keywords:
- C4207
helpviewer_keywords:
- C4207
ms.assetid: f4e09e3e-ac87-4489-8e3f-c8f76b82e721
ms.openlocfilehash: 1ff669512f85dfed9bab307c2986e7858285461d
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80161387"
---
# <a name="compiler-warning-level-4-c4207"></a>コンパイラの警告 (レベル 4) C4207

非標準の拡張機能が使用されています: 拡張初期化子フォーム

Microsoft 拡張機能 (/Ze) では、中かっこ内の文字列を使用して `char` の可変長配列を初期化できます。

## <a name="example"></a>例

```c
// C4207.c
// compile with: /W4
char c[] = { 'a', 'b', "cdefg" }; // C4207

int main()
{
}
```

このような初期化は、ANSI 互換 ([/za](../../build/reference/za-ze-disable-language-extensions.md)) では無効です。
