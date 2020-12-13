---
description: 詳細については、Command-Line Warning D9027 を参照してください。
title: コマンド ラインの警告 D9027
ms.date: 11/04/2016
f1_keywords:
- D9027
helpviewer_keywords:
- D9027
ms.assetid: 2a29edc5-5649-48f2-9058-2057c747284c
ms.openlocfilehash: 8c17750f3310072f8f69c77587a1c17fc9377e79
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97136111"
---
# <a name="command-line-warning-d9027"></a>コマンド ラインの警告 D9027

ソースファイル ' ' が無視されました \<filename>

CL.exe は入力ソースファイルを無視しました。

この警告は、/Fo オプションと、/c オプションを使用したコマンドラインの出力ファイル名の間のスペースによって発生することがあります。 次に例を示します。

```
cl /c /Fo output.obj input.c
```

/Fo との間にはスペースがあるため `output.obj` 、CL.exe は `output.obj` 入力ファイルの名前としてを受け取ります。 この問題を解決するには、領域を削除します。

```
cl /c /Fooutput.obj input.c
```
