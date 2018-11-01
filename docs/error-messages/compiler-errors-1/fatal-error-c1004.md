---
title: 致命的なエラー C1004
ms.date: 11/04/2016
f1_keywords:
- C1004
helpviewer_keywords:
- C1004
ms.assetid: dbe034b0-6eb0-41b4-a50c-2fccf9e78ad4
ms.openlocfilehash: 13fb8963b33569facf62ccedfe9ce8b7bbbbfdc3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50428120"
---
# <a name="fatal-error-c1004"></a>致命的なエラー C1004

予期しないファイルの終わりが見つかりました

コンパイラでは、コンス トラクターを解決せず、ソース ファイルの末尾に達しました。 コードでは、次の要素のいずれかで不足している可能性があります。

- 右中かっこ

- 右かっこ

- 終了コメント マーカー (*/)

- セミコロン

このエラーを解決するには、次を確認します。

- 既定のディスク ドライブの一時ファイルは、ソース ファイルとしての 2 倍の領域に関する必要な領域が不足しています

- `#if`終了を false に評価されるディレクティブ`#endif`ディレクティブ。

- ソース ファイルは、キャリッジ リターンとライン フィードでは終了しません。

次の例では、C1004 が生成されます。

```
// C1004.cpp
#if TEST
int main() {}
// C1004
```

考えられる解決方法:

```
// C1004b.cpp
#if TEST
#endif

int main() {}
```