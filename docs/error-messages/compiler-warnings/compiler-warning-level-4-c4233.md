---
title: コンパイラの警告 (レベル 4) C4233 |Microsoft ドキュメント
ms.custom: ''
ms.date: 10/25/2017
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4233
dev_langs:
- C++
helpviewer_keywords:
- C4233
ms.assetid: 9aa51fc6-8ef3-43b5-bafb-c9333cf60de3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a933d41fd8e7cf3b94e458efff72193b8ce5e187
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33297837"
---
# <a name="compiler-warning-level-4-c4233"></a>コンパイラの警告 (レベル 4) C4233

> 使用される標準の拡張機能: '*キーワード*' キーワードは C++ では、C ではなくのみサポートされます

コンパイラは C++ ではなく、C として、ソース コードをコンパイルし、キーワードは C++ でのみ有効です。 ソース ファイルの拡張子が .c またはを使用する場合、コンパイラが C として、ソース ファイルをコンパイル[/Tc](../../build/reference/tc-tp-tc-tp-specify-source-file-type.md)です。

この警告は、自動的にエラーになります。 この動作を変更する場合は、使用[#pragma 警告](../../preprocessor/warning.md)です。 たとえば、C4233 に、レベル 4 の警告を発行するために、この行をソース コード ファイルに追加します。

```cpp
#pragma warning(4:4233)
```
