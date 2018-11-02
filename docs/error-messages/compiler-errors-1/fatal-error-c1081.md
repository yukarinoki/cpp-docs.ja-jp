---
title: 致命的なエラー C1081
ms.date: 11/04/2016
f1_keywords:
- C1081
helpviewer_keywords:
- C1081
ms.assetid: e58adf17-cbe1-4955-a5c7-80622bbba249
ms.openlocfilehash: f3c9f9bde5da7fb120accbb9a8d72e5715ab9d2b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50569682"
---
# <a name="fatal-error-c1081"></a>致命的なエラー C1081

'symbol': ファイル名が長すぎます

ファイルのパス名の長さを超える`_MAX_PATH`(260 文字では、STDLIB.h で定義)。 ファイルの名前を短きます。

短いファイル名、CL.exe に呼び出す場合、コンパイラは、完全なパス名を生成する必要があります。 たとえば、`cl -c myfile.cpp`を生成するコンパイラが発生する可能性があります。

```
D:\<very-long-directory-path>\myfile.cpp
```