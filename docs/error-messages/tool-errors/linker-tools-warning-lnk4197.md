---
title: リンカー ツールの警告 LNK4197
ms.date: 09/05/2018
f1_keywords:
- LNK4197
helpviewer_keywords:
- LNK4197
ms.assetid: 8a976fd7-a74b-4c83-ab66-a9e7d7073c4a
ms.openlocfilehash: 92702864a00455e4b70f00dfc9988bfb754e2e64
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80183281"
---
# <a name="linker-tools-warning-lnk4197"></a>リンカー ツールの警告 LNK4197

> export '*exportname*' が複数回指定されました。最初の仕様を使用する

エクスポートは複数の異なる方法で指定されます。 リンカーは最初の仕様を使用し、残りは無視します。

C ランタイムライブラリを再構築する場合は、このメッセージを無視してもかまいません。

エクスポートが同じ方法で複数回指定されている場合、リンカーは警告を発行しません。

たとえば、.def ファイルの次の内容では、この警告が発生します。

```
EXPORTS
   functioname      NONAME
   functioname      @10
```

### <a name="to-fix-by-checking-the-following-possible-causes"></a>次のような原因をチェックして問題を解決するには

1. コマンドラインで同じエクスポートが指定されている (export:).def ファイル内にあります。

2. .Def ファイルには、属性が異なる同じエクスポートが2回記述されています。
