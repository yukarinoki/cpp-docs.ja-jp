---
description: 詳細については、Command-Line Warning D9026 を参照してください。
title: コマンド ラインの警告 D9026
ms.date: 11/04/2016
f1_keywords:
- D9026
helpviewer_keywords:
- D9026
ms.assetid: 149fe5e3-5329-4be8-b871-49dfd423aaba
ms.openlocfilehash: 910471215d350f266319f5e14b7bb1a62f641028
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97115483"
---
# <a name="command-line-warning-d9026"></a>コマンド ラインの警告 D9026

オプションはコマンドライン全体に適用されます

ファイル名が指定された後に、コマンドでオプションが指定されました。 このオプションは、その前にあるファイルに適用されていました。

たとえば、コマンドで

```
CL verdi.c /G5 puccini.c
```

ファイル VERDI は、/G4 の既定値ではなく、/G5 オプションを使用してコンパイルされます。

この動作は、以前のバージョンとは異なり、ファイル名の前に指定されたオプションのみが適用されます。その結果、/G4 および PUCCINI を使用してコンパイルされます。 c は/G5. を使用してコンパイルされます。
