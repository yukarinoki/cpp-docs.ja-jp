---
title: コマンド ラインの警告 D9027
ms.date: 11/04/2016
f1_keywords:
- D9027
helpviewer_keywords:
- D9027
ms.assetid: 2a29edc5-5649-48f2-9058-2057c747284c
ms.openlocfilehash: 46ed5750bd1f315f20658ace9b83fac532fbbabb
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80196679"
---
# <a name="command-line-warning-d9027"></a>コマンド ラインの警告 D9027

ソースファイル '\<ファイル名 > ' が無視されました

CL.EXE は入力ソースファイルを無視しました。

この警告は、/Fo オプションと、/c オプションを使用したコマンドラインの出力ファイル名の間のスペースによって発生することがあります。 次に例を示します。

```
cl /c /Fo output.obj input.c
```

/Fo と `output.obj`の間には空白があるため、CL.EXE は入力ファイルの名前として `output.obj` します。 この問題を解決するには、領域を削除します。

```
cl /c /Fooutput.obj input.c
```
