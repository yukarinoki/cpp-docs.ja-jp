---
title: コマンドラインの警告 D9027 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- D9027
dev_langs:
- C++
helpviewer_keywords:
- D9027
ms.assetid: 2a29edc5-5649-48f2-9058-2057c747284c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 105ebbf62027ac3d9377c513c4f7c59e261b983d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46112526"
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