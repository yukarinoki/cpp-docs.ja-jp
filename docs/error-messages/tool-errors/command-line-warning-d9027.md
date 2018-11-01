---
title: コマンド ラインの警告 D9027
ms.date: 11/04/2016
f1_keywords:
- D9027
helpviewer_keywords:
- D9027
ms.assetid: 2a29edc5-5649-48f2-9058-2057c747284c
ms.openlocfilehash: f89e7416efe7a0069ee2dae8df921933bbe76bcf
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50482603"
---
# <a name="command-line-warning-d9027"></a>コマンド ラインの警告 D9027

ソース ファイル '\<filename >' は無視されます

CL.exe では、入力ソース ファイルが無視されます。

この警告は、/Fo オプションおよび/c オプションを使用して、コマンド ラインで、出力ファイル名の間にスペースによることができます。 例えば:

```
cl /c /Fo output.obj input.c
```

/Fo 間にスペースがあるため、および`output.obj`、CL.exe は`output.obj`として、入力ファイルの名前。 問題を解決するには、領域を削除します。

```
cl /c /Fooutput.obj input.c
```