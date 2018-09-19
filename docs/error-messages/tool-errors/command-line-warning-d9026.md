---
title: コマンドラインの警告 D9026 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- D9026
dev_langs:
- C++
helpviewer_keywords:
- D9026
ms.assetid: 149fe5e3-5329-4be8-b871-49dfd423aaba
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 07be633e56dad6c8f0b304a3c88c1b9919221d4a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46079155"
---
# <a name="command-line-warning-d9026"></a>コマンド ラインの警告 D9026

オプションはコマンドライン全体に適用されます。

オプションは、ファイル名を指定したら、コマンドで指定されました。 オプションは、前にそのファイルに適用されました。

たとえば、コマンドで

```
CL verdi.c /G5 puccini.c
```

VERDI.c ファイルは、/G4 の既定値ではない、/G5 オプションを使用してコンパイルされます。

この動作は VERDI.c 結果として、ファイル名の前に指定されたオプションを使用してコンパイル/G4 と異なり/G5 を使用してをコンパイルするだけに適用されるいくつか以前のバージョンと異なる。