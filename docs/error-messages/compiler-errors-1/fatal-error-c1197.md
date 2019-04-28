---
title: 致命的なエラー C1197
ms.date: 11/04/2016
f1_keywords:
- C1197
helpviewer_keywords:
- C1197
ms.assetid: 22b801b7-e792-41f6-a461-973c03c69f25
ms.openlocfilehash: e1c00a001c807b0cc6a5946b61ca4e9d5dc0167a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62229123"
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