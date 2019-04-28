---
title: コンパイラ エラー C3083
ms.date: 11/04/2016
f1_keywords:
- C3083
helpviewer_keywords:
- C3083
ms.assetid: 05ff791d-52bb-41eb-9511-3ef89d7f4710
ms.openlocfilehash: 5ff049d3fcfb2c3dbc28baacdecee9b313574fc0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62243298"
---
# <a name="compiler-error-c3083"></a>コンパイラ エラー C3083

'function': シンボルの左側に、':: ' 型でなければなりません

関数が正しく呼び出されませんでした。

## <a name="example"></a>例

次の例では、C3083 が生成されます。

```
// C3083.cpp
// compile with: /c
struct N {
   ~N();
};

struct N1 {
   ~N1();
};

N::N::~N() {}   // C3083
N1::~N1() {}   // OK
```