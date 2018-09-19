---
title: コンパイラの警告 (レベル 2) C4094 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4094
dev_langs:
- C++
helpviewer_keywords:
- C4094
ms.assetid: e68929fb-3a1c-4be7-920b-d5f79f534f99
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2b9317cbc31ef8bddb14da11af1087a148fd3188
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46078713"
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