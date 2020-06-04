---
title: コマンド ラインの警告 D9026
ms.date: 11/04/2016
f1_keywords:
- D9026
helpviewer_keywords:
- D9026
ms.assetid: 149fe5e3-5329-4be8-b871-49dfd423aaba
ms.openlocfilehash: 59dfcdc97fb9caf60a018cb20583ee6fca3dcb27
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80196704"
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
