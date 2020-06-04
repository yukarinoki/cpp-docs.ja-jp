---
title: コンパイラの警告 (レベル 1) C4138
ms.date: 11/04/2016
f1_keywords:
- C4138
helpviewer_keywords:
- C4138
ms.assetid: 65ebf929-bba0-4237-923b-c1b66adfe17d
ms.openlocfilehash: e1f28f5afb1879229ff0d408cb576312966e1c81
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80200110"
---
# <a name="compiler-warning-level-1-c4138"></a>コンパイラの警告 (レベル 1) C4138

始まりのデリミターがない閉じのコメントデリミター (*/) が見つかりました。

終了のコメント区切り記号の前に、開始のコメント区切り記号がありません。 コンパイラでは、アスタリスク (<strong>\*</strong>) とスラッシュ (/) との間にスペースが必要です。

## <a name="example"></a>例

```cpp
// C4138a.cpp
// compile with: /W1
int */*comment*/ptr;   // C4138 Ambiguous first delimiter causes warning
int main()
{
}
```

この警告は、コメントを入れ子にしようとすると、発生する可能性があります。

この警告は、コメントを含むコードのセクションをコメント アウトして、 **#if/#endif** ブロックでコードを囲み、制御式を 0 に設定すると、解決する場合があります。

```cpp
// C4138b.cpp
// compile with: /W1
#if 0
int my_variable;   /* Declaration currently not needed */
#endif
int main()
{
}
```
