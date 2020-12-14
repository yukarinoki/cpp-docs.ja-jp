---
description: '詳細情報: 致命的なエラー C1004'
title: 致命的なエラー C1004
ms.date: 11/04/2016
f1_keywords:
- C1004
helpviewer_keywords:
- C1004
ms.assetid: dbe034b0-6eb0-41b4-a50c-2fccf9e78ad4
ms.openlocfilehash: f21978f5ff314a8273dde60428dc89ca0c5767b0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97262686"
---
# <a name="fatal-error-c1004"></a>致命的なエラー C1004

予期しないファイルの終わりが見つかりました

コンパイラは、コンストラクトを解決せずにソースファイルの末尾に到達しました。 次のいずれかの要素がコードに含まれていない可能性があります。

- 右中かっこ

- 右かっこ

- 終了コメントマーカー (*/)

- セミコロン

このエラーを解決するには、次のことを確認します。

- 既定のディスクドライブには、一時ファイル用に十分な領域がありません。そのためには、ソースファイルと比べて約2倍の領域が必要になります。

- `#if`False に評価されるディレクティブには、終了 `#endif` ディレクティブがありません。

- ソースファイルがキャリッジリターンとラインフィードで終了していません。

次の例では、C1004 が生成されます。

```cpp
// C1004.cpp
#if TEST
int main() {}
// C1004
```

考えられる解決策:

```cpp
// C1004b.cpp
#if TEST
#endif

int main() {}
```
