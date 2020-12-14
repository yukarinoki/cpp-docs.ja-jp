---
description: '詳細情報: コンパイラの警告 (レベル 1) C4829'
title: コンパイラの警告 (レベル 1) C4829
ms.date: 11/04/2016
f1_keywords:
- C4829
helpviewer_keywords:
- C4829
ms.assetid: 4ffabe2b-2ddc-4c52-8564-d1355c93cfa6
ms.openlocfilehash: ae44c50e7b680dff94427896eea2e10c4ed33483
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97198025"
---
# <a name="compiler-warning-level-1-c4829"></a>コンパイラの警告 (レベル 1) C4829

関数 main への正しくないパラメーターである可能性があります。 ' Intmain (Platform:: Array \<Platform::String^> ^ argv) ' を検討してください。

main などの特定の関数は、参照型パラメーターを受け取れません。 コンパイルは成功しても、結果のイメージは実行できない場合があります。

次の例では C4829 が生成されます。

```cpp
// C4829.cpp
// compile by using: cl /EHsc /ZW /W4 /c C4829.cpp
int main(Platform::String ^ s) {}   // C4829
```
