---
title: コンパイラの警告 (レベル 2) C4094
ms.date: 11/04/2016
f1_keywords:
- C4094
helpviewer_keywords:
- C4094
ms.assetid: e68929fb-3a1c-4be7-920b-d5f79f534f99
ms.openlocfilehash: 73805afc897d14c6d2cc87490dfa0769a8de5193
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62350518"
---
# <a name="compiler-warning-level-2-c4094"></a>コンパイラの警告 (レベル 2) C4094

タグ付けされていない ' token' シンボルが宣言されていません。

タグのない構造体、共用体、またはクラスを使用して空の宣言が検出されました。 宣言は無視されます。

## <a name="example"></a>例

```
// C4094.cpp
// compile with: /W2
struct
{
};   // C4094

int main()
{
}
```

この条件には、ANSI 互換の下にエラーが生成されます ([/Za](../../build/reference/za-ze-disable-language-extensions.md))。