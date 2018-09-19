---
title: 記述ブロック |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- description blocks
- NMAKE program, description blocks
- blocks, description
ms.assetid: 1321f228-d389-40ac-b0cd-4f6e9293602b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d83e010f690f96afa5a57eb89ca1e8f4cf444225
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45699661"
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