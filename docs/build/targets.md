---
title: ターゲット |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- targets, specifying in NMAKE
ms.assetid: 826ee849-4278-4c6e-97c3-79a2b5fe6463
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 79e9d72d2b2fb999d987a6781caace9a0360facb
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32380263"
---
# <a name="targets"></a>ターゲット
依存関係行で、有効なファイル名、ディレクトリ名を使用して、1 つまたは複数のターゲットを指定または[疑似ターゲット](../build/pseudotargets.md)です。 1 つ以上のスペースまたはタブで複数のターゲットを区切ります。 ターゲットは、大文字と小文字が区別されません。 ファイル名を持つ、パスを指定します。 ターゲットは、256 文字を超えることはできません。 コロンの前のターゲットが 1 つの文字の場合は、区切るスペース; を使用してください。それ以外の場合 (nmake の) は、ドライブ指定子として文字とコロンの組み合わせを解釈します。  
  
## <a name="what-do-you-want-to-know-more-about"></a>さらに詳しくは次のトピックをクリックしてください  
 [擬似ターゲット](../build/pseudotargets.md)  
  
 [複数のターゲット](../build/multiple-targets.md)  
  
 [依存関係](../build/cumulative-dependencies.md)  
  
 [複数の記述ブロック内のターゲット](../build/targets-in-multiple-description-blocks.md)  
  
 [依存関係の副作用](../build/dependency-side-effects.md)  
  
## <a name="see-also"></a>関連項目  
 [記述ブロック](../build/description-blocks.md)