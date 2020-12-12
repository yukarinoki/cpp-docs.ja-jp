---
description: 詳細については、「メイクファイル内のコマンド」を参照してください。
title: メイクファイルのコマンド
ms.date: 11/04/2016
helpviewer_keywords:
- commands, makefiles
ms.assetid: 8085517e-42f4-493b-b8f8-44311fc08c64
ms.openlocfilehash: a4f3c6d3cc9b5d567548d7b3f2bd7679d492ebf0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97179084"
---
# <a name="commands-in-a-makefile"></a>メイクファイルのコマンド

説明ブロックまたは推論規則は、依存関係が古くなった場合に実行するコマンドのブロックを指定します。 コマンドを実行する前に NMAKE によって表示されます (/S の場合を除く) **。サイレント**、 **!CMDSWITCHES** または \@ が使用されます。 説明ブロックの後にコマンドブロックがない場合、NMAKE は一致する推論規則を検索します。

Commands ブロックには、それぞれ独自の行に1つ以上のコマンドが含まれています。 依存関係またはルールとコマンドブロックの間に空白行を表示することはできません。 ただし、スペースまたはタブだけを含む行を表示できます。この行は null コマンドとして解釈され、エラーは発生しません。 コマンドライン間で空白行を使用することはできません。

コマンドラインは、1つ以上のスペースまたはタブで始まります。 バックスラッシュ (\) の後に改行文字を入力すると、コマンド内でスペースとして解釈されます。行の末尾に円記号を使用して、次の行にコマンドを続けます。 NMAKE では、スペースやタブなどの他の文字が円記号の後に続く場合、円記号は文字どおりに解釈されます。

コマンドの前にセミコロン (;)コマンドブロックが次のようになっているかどうかにかかわらず、依存関係の行または推論規則に表示されます。

```
project.obj : project.c project.h ; cl /c project.c
```

## <a name="what-do-you-want-to-know-more-about"></a>さらに詳しくは次のトピックをクリックしてください

[コマンド修飾子](command-modifiers.md)

[ファイル名分割構文](filename-parts-syntax.md)

[メイクファイルのインライン ファイル](inline-files-in-a-makefile.md)

## <a name="see-also"></a>関連項目

[NMAKE のリファレンス](nmake-reference.md)
