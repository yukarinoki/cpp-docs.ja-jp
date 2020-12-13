---
description: '詳細情報: コンパイラの警告 (レベル 4) C4233'
title: コンパイラの警告 (レベル 4) C4233
ms.date: 10/25/2017
f1_keywords:
- C4233
helpviewer_keywords:
- C4233
ms.assetid: 9aa51fc6-8ef3-43b5-bafb-c9333cf60de3
ms.openlocfilehash: 3e797bcefeaeee615014ea8e0bd109e4cf4ffbef
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97344017"
---
# <a name="compiler-warning-level-4-c4233"></a>コンパイラの警告 (レベル 4) C4233

> 非標準の拡張機能が使用されています: '*keyword*' キーワードは c ではなく C++ でのみサポートされています。

コンパイラは C++ ではなく C としてソースコードをコンパイルしましたが、C++ でのみ有効なキーワードを使用しました。 ソースファイルの拡張子が .c の場合、または [/tc](../../build/reference/tc-tp-tc-tp-specify-source-file-type.md)を使用する場合、コンパイラはソースファイルを c としてコンパイルします。

この警告は、自動的にエラーになります。 この動作を変更する場合は、 [#pragma 警告](../../preprocessor/warning.md)を使用します。 たとえば、C4233 をレベル4の警告問題にするには、次の行をソースコードファイルに追加します。

```cpp
#pragma warning(4:4233)
```
