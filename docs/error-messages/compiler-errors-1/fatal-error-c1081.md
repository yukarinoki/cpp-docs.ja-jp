---
title: 致命的なエラー C1081 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1081
dev_langs:
- C++
helpviewer_keywords:
- C1081
ms.assetid: e58adf17-cbe1-4955-a5c7-80622bbba249
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b34f2f19a0bb8770ea9292fef120c415c0fb255a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46060532"
---
# <a name="fatal-error-c1081"></a>致命的なエラー C1081

'symbol': ファイル名が長すぎます

ファイルのパス名の長さを超える`_MAX_PATH`(260 文字では、STDLIB.h で定義)。 ファイルの名前を短きます。

短いファイル名、CL.exe に呼び出す場合、コンパイラは、完全なパス名を生成する必要があります。 たとえば、`cl -c myfile.cpp`を生成するコンパイラが発生する可能性があります。

```
D:\<very-long-directory-path>\myfile.cpp
```