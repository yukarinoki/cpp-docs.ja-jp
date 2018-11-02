---
title: 記述ブロック
ms.date: 11/04/2016
helpviewer_keywords:
- description blocks
- NMAKE program, description blocks
- blocks, description
ms.assetid: 1321f228-d389-40ac-b0cd-4f6e9293602b
ms.openlocfilehash: 214963b5c3f633e8d029cee0500d4bd5fab6ed53
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50490607"
---
# <a name="description-blocks"></a>記述ブロック

記述ブロックでは、コマンドのブロックの後に必要に応じて依存関係の行を示します。

```
targets... : dependents...
    commands...
```

依存関係の行では、1 つまたは複数のターゲットと 0 個以上の依存ファイルを指定します。 ターゲットは、行の先頭にあります。 コロン (:) での依存から個別のターゲットはスペースまたはタブが許可されます。 行を分割するには、ターゲットまたは依存の後に円記号 (\) を使用します。 ターゲットが存在しない場合、依存より早いタイムスタンプを持つかが、[疑似ターゲット](../build/pseudotargets.md)、NMAKE コマンドを実行します。 相互に依存するは、ターゲットを別の場所しが存在しないか、独自の依存オブジェクトと比べて古い場合、(nmake の) は、現在の依存関係を更新する前に、依存を更新します。

## <a name="what-do-you-want-to-know-more-about"></a>さらに詳しくは次のトピックをクリックしてください

[ターゲット](../build/targets.md)

[依存](../build/dependents.md)

## <a name="see-also"></a>関連項目

[NMAKE リファレンス](../build/nmake-reference.md)