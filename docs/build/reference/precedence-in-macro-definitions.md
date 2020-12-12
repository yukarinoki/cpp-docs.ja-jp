---
description: '詳細情報: マクロ定義における優先順位'
title: マクロ定義の優先順位
ms.date: 11/04/2016
helpviewer_keywords:
- NMAKE program, precedence in macro definitions
- macros, precedence
ms.assetid: 0c13182d-83cb-4cbd-af2d-f4c916b62aeb
ms.openlocfilehash: 1738c4ba77f330103395278a6daae169b04fae4c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97225896"
---
# <a name="precedence-in-macro-definitions"></a>マクロ定義の優先順位

マクロに複数の定義がある場合、NMAKE は最も優先順位の高い定義を使用します。 次の一覧に、優先順位の高い順を示します。

1. コマンドラインで定義されたマクロ

1. メイクファイルまたはインクルードファイルで定義されたマクロ

1. 継承された環境変数マクロ

1. Tools.ini ファイルで定義されているマクロ

1. [CC](command-macros-and-options-macros.md)や[as](command-macros-and-options-macros.md)などの定義済みマクロ

/E を使用して、環境変数から継承されたマクロが同じ名前のメイクファイルマクロをオーバーライドするようにします。 を使用し **ます。UNDEF** は、コマンドラインをオーバーライドします。

## <a name="see-also"></a>関連項目

[NMAKE マクロの定義](defining-an-nmake-macro.md)
