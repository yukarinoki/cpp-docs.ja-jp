---
title: マクロ定義の優先順位
ms.date: 11/04/2016
helpviewer_keywords:
- NMAKE program, precedence in macro definitions
- macros, precedence
ms.assetid: 0c13182d-83cb-4cbd-af2d-f4c916b62aeb
ms.openlocfilehash: 8829b3cdbc7b2324ef3d118f8ca45dd2a1621e7e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50619081"
---
# <a name="precedence-in-macro-definitions"></a>マクロ定義の優先順位

マクロに複数の定義がある場合は、NMAKE が最も高い優先順位の定義を使用します。 次に、高いものから、優先順位の順序を示します。

1. コマンドラインで定義されているマクロ

1. マクロは、メイクファイルで定義されているか、ファイルを含める

1. 継承の環境変数マクロ

1. Tools.ini ファイルで定義されているマクロ

1. 定義済みマクロなど[CC](../build/command-macros-and-options-macros.md)と[AS](../build/command-macros-and-options-macros.md)

/E を使用して、同じ名前のメイクファイルのマクロをオーバーライドする環境変数から継承されたマクロが発生します。 使用 **!UNDEF**コマンドラインを上書きします。

## <a name="see-also"></a>関連項目

[NMAKE マクロの定義](../build/defining-an-nmake-macro.md)