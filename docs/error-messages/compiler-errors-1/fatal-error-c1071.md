---
title: 致命的なエラー C1071
ms.date: 11/04/2016
f1_keywords:
- C1071
helpviewer_keywords:
- C1071
ms.assetid: 489f1786-370e-4ecd-af67-538fe6e5bd4e
ms.openlocfilehash: 8fe6b0f3bb1253f72c97f29070ba81cdbdf80508
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50506705"
---
# <a name="fatal-error-c1071"></a>致命的なエラー C1071

コメント内で予期しない EOF が見つかりました。

コンパイラでは、コメントのスキャン中に、ファイルの末尾に達しました。

### <a name="to-fix-by-checking-the-following-possible-causes"></a>次のような原因をチェックして問題を解決するには

1. コメントの終端記号がありません (*/)。

1. ソース ファイルの最後の行でのコメントの後ろに改行文字がありません。

次の例では、C1071 が生成されます。

```
// C1071.cpp
int main() {
}

/* this comment is fine */
/* forgot the closing tag        // C1071
```