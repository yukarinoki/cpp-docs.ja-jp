---
title: 致命的なエラー C1197 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1197
dev_langs:
- C++
helpviewer_keywords:
- C1197
ms.assetid: 22b801b7-e792-41f6-a461-973c03c69f25
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 58561e7bd906fc750779ef53a4f68ec27088a3b7
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46024763"
---
# <a name="fatal-error-c1197"></a>致命的なエラー C1197

プログラムが既に 'mscorlib.dll_2' を参照 'mscorlib.dll_1' を参照することはできません。

コンパイラは、共通言語ランタイムのバージョンに一致します。  ただし、しようとしましたが、以前のバージョンから共通言語ランタイム ファイルのバージョンを参照します。

このエラーを解決するのには、Visual C のバージョンに同梱されている共通言語ランタイムのバージョンからのみ参照ファイルは、コンパイルしています。

## <a name="example"></a>例

次の例では、C1197 が生成されます。

```
// C1197.cpp
// compile with: /clr /c
// processor: x86
#using "C:\Windows\Microsoft.NET\Framework\v1.1.4322\mscorlib.dll"   // C1197
// try the following line instead
// #using "mscorlib.dll"
```