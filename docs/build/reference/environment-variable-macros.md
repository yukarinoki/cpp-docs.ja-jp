---
description: '詳細情報: Environment-Variable マクロ'
title: 環境変数マクロ
ms.date: 11/04/2016
helpviewer_keywords:
- NMAKE program, environment variable macros
- environment variables, macros in NMAKE
- macros, environment-variable
ms.assetid: f8e96635-0906-47b0-9f56-12a6fdf5e347
ms.openlocfilehash: b7beaf8f3e98ea7447d798041f7531ed5da671ce
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97192591"
---
# <a name="environment-variable-macros"></a>環境変数マクロ

NMAKE は、セッションの開始前に存在する環境変数のマクロ定義を継承します。 変数がオペレーティングシステム環境で設定されている場合は、NMAKE マクロとして使用できます。 継承された名前は大文字に変換されます。 継承は、前処理の前に発生します。 /E オプションを使用すると、環境変数から継承されたマクロは、メイクファイルで同じ名前のマクロをオーバーライドできます。

環境変数マクロは、セッションで再定義できます。これにより、対応する環境変数が変更されます。 SET コマンドを使用して環境変数を変更することもできます。 ただし、SET コマンドを使用してセッション内の環境変数を変更しても、対応するマクロは変更されません。

次に例を示します。

```
PATH=$(PATH);\nonesuch

all:
    echo %%PATH%%
```

この例では、を変更すると、 `PATH` 対応する環境変数が変更され、 `PATH` パスにが追加さ `\nonesuch` れます。

メイクファイルで構文が正しくない文字列として環境変数が定義されている場合、マクロは作成されず、警告は生成されません。 変数の値にドル記号 ($) が含まれている場合、NMAKE はマクロ呼び出しの開始として解釈します。 マクロを使用すると、予期しない動作が発生する可能性があります。

## <a name="see-also"></a>関連項目

[特別な NMAKE マクロ](special-nmake-macros.md)
