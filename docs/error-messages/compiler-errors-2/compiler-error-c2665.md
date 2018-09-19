---
title: コンパイラ エラー C2665 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2665
dev_langs:
- C++
helpviewer_keywords:
- C2665
ms.assetid: a7f99b61-2eae-4f2b-ba75-ea68fd1e8312
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b442e1de0481ef3d00742ed201575526332decff
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46109146"
---
# <a name="compiler-error-c2665"></a>コンパイラ エラー C2665

'function': パラメーターの数値 2 を型 'type' から変換 number1 オーバー ロードはないことができます

オーバー ロードされた関数のパラメーターは、必要な型に変換できません。  考えられる解決策:

- 変換演算子を指定します。

- 明示的な変換を使用します。

## <a name="example"></a>例

次の例では、C2665 が生成されます。

```
// C2665.cpp
void func(short, char*){}
void func(char*, char*){}

int main() {
   func(0, 1);   // C2665
   func((short)0, (char*)1);   // OK
}
```