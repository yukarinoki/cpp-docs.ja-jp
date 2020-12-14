---
description: '詳細情報: コンパイラの警告 (レベル 4) C4295'
title: コンパイラの警告 (レベル 4) C4295
ms.date: 01/09/2018
f1_keywords:
- C4295
helpviewer_keywords:
- C4295
ms.assetid: 20dbff85-9f62-4ca3-8fe9-079d4512006d
ms.openlocfilehash: 77f94d96d7ce5659652296e814777341a310a19f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97294588"
---
# <a name="compiler-warning-level-4-c4295"></a>コンパイラの警告 (レベル 4) C4295

> '*array*': 配列が小さすぎるため、終端の null 文字を含めることができません

配列は初期化されましたが、配列の最後の文字が null ではありません。配列に文字列としてアクセスすると、予期しない結果が生じる可能性があります。

## <a name="example"></a>例

次の例では、C4295 が生成されます。 この問題を解決するには、配列のサイズを大きく宣言し、初期化子文字列から終端の null を保持するか、配列初期化子リストを使用して、これが null で終わる文字列ではなくの配列であることを明確にすることができ **`char`** ます。

```C
// C4295.c
// compile with: /W4

int main() {
   char a[3] = "abc";           // C4295
   char b[3] = {'d', 'e', 'f'}; // No warning
   a[0] = b[2];
}
```
