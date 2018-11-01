---
title: コンパイラの警告 (レベル 1) C4829
ms.date: 11/04/2016
f1_keywords:
- C4829
helpviewer_keywords:
- C4829
ms.assetid: 4ffabe2b-2ddc-4c52-8564-d1355c93cfa6
ms.openlocfilehash: ace409cee05650e0dbfbcdd32cd15e85f8dbf006
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50594169"
---
# <a name="compiler-warning-level-1-c4829"></a>コンパイラの警告 (レベル 1) C4829

関数 main への正しくないパラメーターである可能性があります。 検討 ' intmain (platform::array\<platform::string ^ > ^ argv)'

main などの特定の関数は、参照型パラメーターを受け取れません。 コンパイルは成功しても、結果のイメージは実行できない場合があります。

次の例では C4829 が生成されます。

```
// C4829.cpp
// compile by using: cl /EHsc /ZW /W4 /c C4829.cpp
int main(Platform::String ^ s) {}   // C4829

```