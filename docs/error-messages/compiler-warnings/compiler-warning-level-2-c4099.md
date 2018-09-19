---
title: コンパイラの警告 (レベル 2) C4099 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4099
dev_langs:
- C++
helpviewer_keywords:
- C4099
ms.assetid: 00bb803d-cae7-4ab8-8969-b46f54139ac8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2d7ffee02e8e5414a0e06cc4ba0da77a50c75f53
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46110173"
---
# <a name="compiler-warning-level-2-c4099"></a>コンパイラの警告 (レベル 2) C4099

'identifier': 型名が 'objecttype1' '%objecttype2' を使用して認識を使用して最初の表示

クラスと構造体として宣言されたオブジェクトが定義されているか、クラスとして宣言されたオブジェクトが構造体として定義されています。 コンパイラは、定義で指定された型を使用します。

## <a name="example"></a>例

次の例では、C4099 が生成されます。

```
// C4099.cpp
// compile with: /W2 /c
struct A;
class A {};   // C4099, use different identifer or use same object type
```