---
description: '詳細情報: 致命的なエラー C1081'
title: 致命的なエラー C1081
ms.date: 11/04/2016
f1_keywords:
- C1081
helpviewer_keywords:
- C1081
ms.assetid: e58adf17-cbe1-4955-a5c7-80622bbba249
ms.openlocfilehash: 97e1070cb24a70750e9c7d9f78a3860b26a7831a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97330703"
---
# <a name="fatal-error-c1081"></a>致命的なエラー C1081

' symbol ': ファイル名が長すぎます。

ファイルのパス名の長さが、 `_MAX_PATH` (stdlib.h> によって260文字として定義されている) を超えています。 ファイルの名前を短くします。

短いファイル名を使用して CL.exe を呼び出すと、コンパイラは完全なパス名を生成することが必要になる場合があります。 たとえば、によって、 `cl -c myfile.cpp` コンパイラによってが生成される場合があります。

```
D:\<very-long-directory-path>\myfile.cpp
```
