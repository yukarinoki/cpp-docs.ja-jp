---
title: コンパイラの警告 (レベル 1) C4829
ms.date: 11/04/2016
f1_keywords:
- C4829
helpviewer_keywords:
- C4829
ms.assetid: 4ffabe2b-2ddc-4c52-8564-d1355c93cfa6
ms.openlocfilehash: a5c7cd062f22e9888e484f6d254fcf173cf83d1a
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80199382"
---
# <a name="compiler-warning-level-1-c4829"></a>コンパイラの警告 (レベル 1) C4829

関数 main への正しくないパラメーターである可能性があります。 ' Intmain (Platform:: Array\<Platform:: String ^ > ^ argv) ' を検討してください

main などの特定の関数は、参照型パラメーターを受け取れません。 コンパイルは成功しても、結果のイメージは実行できない場合があります。

次の例では C4829 が生成されます。

```cpp
// C4829.cpp
// compile by using: cl /EHsc /ZW /W4 /c C4829.cpp
int main(Platform::String ^ s) {}   // C4829
```
