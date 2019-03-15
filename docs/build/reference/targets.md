---
title: ターゲット
ms.date: 11/04/2016
helpviewer_keywords:
- targets, specifying in NMAKE
ms.assetid: 826ee849-4278-4c6e-97c3-79a2b5fe6463
ms.openlocfilehash: 4bb80b01993ee3f3715f551c73337cf24cd43f2c
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2019
ms.locfileid: "57826621"
---
# <a name="targets"></a>ターゲット

依存関係の行で任意の有効なファイル名、ディレクトリの名前を使用して、1 つまたは複数のターゲットを指定または[疑似ターゲット](pseudotargets.md)します。 1 つ以上のスペースまたはタブでは、複数のターゲットを区切ります。 ターゲットは、大文字小文字が区別されません。 ファイル名、パスを指定します。 ターゲットは、256 文字を超えることはできません。 コロンの前のターゲットが 1 つの文字の場合は、区切りのスペースを使用して、それ以外の場合、(nmake の) は、ドライブ指定子として文字とコロンの組み合わせを解釈します。

## <a name="what-do-you-want-to-know-more-about"></a>さらに詳しくは次のトピックをクリックしてください

[擬似ターゲット](pseudotargets.md)

[複数のターゲット](multiple-targets.md)

[累積的な依存関係](cumulative-dependencies.md)

[ターゲットの複数の記述ブロック](targets-in-multiple-description-blocks.md)

[依存関係の副作用](dependency-side-effects.md)

## <a name="see-also"></a>関連項目

[記述ブロック](description-blocks.md)