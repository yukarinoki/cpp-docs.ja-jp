---
title: メイクファイルの特殊文字 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- NMAKE program, special characters
- makefiles, special characters
- special characters, in NMAKE macros
- macros, special characters
ms.assetid: 92c34ab5-ca6b-4fc0-bcf4-3172eaeda9f0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3ae77e769672dcc88a9dd41c901424c8c8150e6b
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45709364"
---
# <a name="special-characters-in-a-makefile"></a>メイクファイルの特殊文字

NMAKE の特殊文字をリテラル文字として使用するには、その前にキャレット (^) を配置します。 NMAKE では、その他の文字の前にキャレットを無視します。 特殊文字は次のとおりです。

`:  ;  #  (  )  $  ^  \  {  }  !  @  —`

引用符で囲まれた文字列内のキャレット (^) は、キャレットのリテラル文字として扱われます。 行の末尾のキャレットは、文字列またはマクロでリテラルの改行文字を挿入します。

マクロ、円記号 (\\) の後に改行文字がスペースで置き換えられます。

コマンドでは、パーセント記号 (%) は、ファイル指定子が。 コマンドでは文字どおり % を表すためを 1 つの代わりに 2 つのパーセント記号 (%) を指定します。 その他の状況で (nmake の) 解釈単一の % をそのまま使いますが、常に double 型の値を解釈 %% として単一の % です。 そのため、リテラルを表す %%、3 つのパーセント記号をいずれかを指定 %%%c、または 4 つのパーセント記号、%%%c。

ドル記号 ($) をコマンドにリテラル文字として使用するには、2 つのドル記号 ($$) を指定します。 このメソッドは、他の状況でも使用できます、^ $ 動作します。

## <a name="see-also"></a>関連項目

[メイクファイルの内容](../build/contents-of-a-makefile.md)