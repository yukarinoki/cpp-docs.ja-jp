---
description: '詳細情報: 致命的なエラー C1071'
title: 致命的なエラー C1071
ms.date: 11/04/2016
f1_keywords:
- C1071
helpviewer_keywords:
- C1071
ms.assetid: 489f1786-370e-4ecd-af67-538fe6e5bd4e
ms.openlocfilehash: c4a6734dcb515b6d495eac720f83ba39be3c3677
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97344381"
---
# <a name="fatal-error-c1071"></a>致命的なエラー C1071

コメント内で予期しない EOF が見つかりました。

コメントのスキャン中に、コンパイラがファイルの末尾に到達しました。

### <a name="to-fix-by-checking-the-following-possible-causes"></a>次のような原因をチェックして問題を解決するには

1. コメント終端記号 (*/) がありません。

1. ソースファイルの最後の行にあるコメントの後に改行文字がありません。

次の例では、C1071 が生成されます。

```cpp
// C1071.cpp
int main() {
}

/* this comment is fine */
/* forgot the closing tag        // C1071
```
