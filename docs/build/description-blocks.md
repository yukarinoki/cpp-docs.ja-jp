---
title: 記述ブロック |Microsoft ドキュメント
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
ms.openlocfilehash: 0784f08c479a8c8f3968ef61a01431cd9e0ca71e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32367109"
---
# <a name="description-blocks"></a>記述ブロック
記述ブロックは、必要に応じて、コマンドのブロックが後に依存関係行を示します。  
  
```  
targets... : dependents...  
    commands...  
```  
  
 依存関係行は、1 つまたは複数のターゲットと 0 個以上の依存ファイルを指定します。 ターゲットは、行の先頭にする必要があります。 参照先のコロン (:) から別のターゲットの以外の場合はスペースまたはタブが許可されます。 行を分割するには、ターゲットまたは依存の後に円記号 (\) を使用します。 ターゲットが存在しない場合、依存するより早いタイムスタンプを持つかが、[疑似ターゲット](../build/pseudotargets.md)NMAKE のコマンドを実行します。 相互に依存するは、ターゲットを別の場所が存在しないか、独自の依存オブジェクトと比べて古い場合、(nmake の) は、現在の依存関係を更新する前に、依存を更新します。  
  
## <a name="what-do-you-want-to-know-more-about"></a>さらに詳しくは次のトピックをクリックしてください  
 [ターゲット](../build/targets.md)  
  
 [依存](../build/dependents.md)  
  
## <a name="see-also"></a>関連項目  
 [NMAKE リファレンス](../build/nmake-reference.md)