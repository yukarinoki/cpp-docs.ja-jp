---
title: コンパイラの警告 (レベル 4) C4233
ms.date: 10/25/2017
f1_keywords:
- C4233
helpviewer_keywords:
- C4233
ms.assetid: 9aa51fc6-8ef3-43b5-bafb-c9333cf60de3
ms.openlocfilehash: 361e00b7361aab51ea077d7e248503f3654e5e58
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50516520"
---
# <a name="compiler-warning-level-4-c4233"></a>コンパイラの警告 (レベル 4) C4233

> 標準の拡張機能を使用します '*キーワード*' キーワードが C++、C ではなくでのみサポートされます。

コンパイラが C++ ではなく C としてソース コードをコンパイルし、有効な C++ のキーワードを使用します。 ソース ファイルの拡張子が .c またはを使用する場合、コンパイラが C として、ソース ファイルをコンパイル[/Tc](../../build/reference/tc-tp-tc-tp-specify-source-file-type.md)します。

この警告は、自動的にエラーになります。 この動作を変更する場合を使用して、 [#pragma warning](../../preprocessor/warning.md)します。 たとえば、C4233 に、レベル 4 の警告を発行するために、この行をソース コード ファイルに追加します。

```cpp
#pragma warning(4:4233)
```
