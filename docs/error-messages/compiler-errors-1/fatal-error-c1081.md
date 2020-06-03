---
title: 致命的なエラー C1081
ms.date: 11/04/2016
f1_keywords:
- C1081
helpviewer_keywords:
- C1081
ms.assetid: e58adf17-cbe1-4955-a5c7-80622bbba249
ms.openlocfilehash: b8630a26d14c68a5f1abe45bb0b8d0141d0dedbb
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80204192"
---
# <a name="fatal-error-c1081"></a>致命的なエラー C1081

' symbol ': ファイル名が長すぎます。

ファイルのパス名の長さが `_MAX_PATH` を超えています (STDLIB.H> によって260文字として定義されています)。 ファイルの名前を短くします。

短いファイル名を使用して CL.EXE を呼び出すと、コンパイラは完全なパス名を生成する必要がある場合があります。 たとえば、`cl -c myfile.cpp` によって、コンパイラによってが生成される可能性があります。

```
D:\<very-long-directory-path>\myfile.cpp
```
