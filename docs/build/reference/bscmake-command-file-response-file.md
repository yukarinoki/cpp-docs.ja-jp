---
description: '詳細情報: BSCMAKE コマンドファイル (応答ファイル)'
title: BSCMAKE コマンド ファイル (応答ファイル)
ms.date: 11/04/2016
helpviewer_keywords:
- BSCMAKE, response file
- BSCMAKE, command file
- response files, BSCMAKE
- command files, BSCMAKE
- response files
- command files
ms.assetid: abdffeea-35c7-4f2d-8c17-7d0d80bac314
ms.openlocfilehash: 4bb321cd7aa705d7e33d0f539ab3e0aa2e3cb8bf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97187157"
---
# <a name="bscmake-command-file-response-file"></a>BSCMAKE コマンド ファイル (応答ファイル)

> [!WARNING]
> BSCMAKE は、現在も Visual Studio と共にインストールされていますが、IDE では使用されなくなりました。 Visual Studio 2008 以降、ブラウザーとシンボルの情報は、ソリューション フォルダー内の SQL Server の .sdf ファイルに自動的に格納されます。

コマンドファイルには、コマンドライン入力の一部またはすべてを指定できます。 次の構文を使用して、コマンドファイルを指定します。

```
BSCMAKE @filename
```

コマンドファイルは1つだけ許可されます。 *Filename* でパスを指定できます。 *Filename* の前にアットマーク ( **\@** ) を付けます。 BSCMAKE では、拡張機能は想定されていません。 *ファイル名* の後にコマンドラインで追加の *sbrfiles* を指定できます。 コマンドファイルは、コマンドラインで指定するのと同じ順序で BSCMAKE への入力を含むテキストファイルです。 コマンドライン引数を1つ以上のスペース、タブ、または改行文字で区切ります。

次のコマンドは、コマンドファイルを使用して BSCMAKE を呼び出します。

```
BSCMAKE @prog1.txt
```

コマンドファイルの例を次に示します。

```
/n /v /o main.bsc /El
/S (
toolbox.h
verdate.h c:\src\inc\screen.h
)
file1.sbr file2.sbr file3.sbr file4.sbr
```

## <a name="see-also"></a>関連項目

[BSCMAKE リファレンス](bscmake-reference.md)
