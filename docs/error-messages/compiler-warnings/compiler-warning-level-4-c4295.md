---
title: コンパイラの警告 (レベル 4) C4295 |Microsoft Docs
ms.custom: ''
ms.date: 1/09/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4295
dev_langs:
- C++
helpviewer_keywords:
- C4295
ms.assetid: 20dbff85-9f62-4ca3-8fe9-079d4512006d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 63c7a6b640039f6e3008cab924c9d58dfcb1fcc8
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50080612"
---
# <a name="compiler-warning-level-4-c4295"></a>コンパイラの警告 (レベル 4) C4295

> '*配列*': 配列が小さすぎる、終端の null 文字を含める

配列が初期化されましたが、配列の最後の文字が null ではありません。文字列として配列にアクセスすると、予期しない結果が生じる場合があります。

## <a name="example"></a>例

次の例では、C4295 が生成されます。 この問題を解決する可能性がありますを宣言する、配列のサイズを保持するより大きなから、初期化子の文字列または終端の null は、配列初期化子リストを使用しての配列である、インテントをオフにする可能性があります`char`null で終わる文字列ではありません。

```C
// C4295.c
// compile with: /W4

int main() {
   char a[3] = "abc";           // C4295
   char b[3] = {'d', 'e', 'f'}; // No warning
   a[0] = b[2];
}
```
