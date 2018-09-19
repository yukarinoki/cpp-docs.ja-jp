---
title: コンパイラの警告 (レベル 1) C4091 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4091
dev_langs:
- C++
helpviewer_keywords:
- C4091
ms.assetid: 3a404967-ab42-49b0-b324-fd7ba1859d78
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7b8fd377ed8b1f6425f0a1c13a83531fca1b797f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46114099"
---
# <a name="compiler-warning-level-1-c4091"></a>コンパイラの警告 (レベル 1) C4091

'keyword': 'type' の左側で変数が宣言されていない場合は無視されます

ユーザーには、変数を宣言するには、おそらく対象としていますが、コンパイラによって、変数を宣言されませんでした、状況が検出されました。

## <a name="example"></a>例

A`__declspec`属性、ユーザー定義型の宣言の先頭にその型の変数に適用されます。 C4091 では、変数が宣言されていないことを示します。 次の例では、C4091 が生成されます。

```
// C4091.cpp
// compile with: /W1 /c
__declspec(dllimport) class X {}; // C4091

// __declspec attribute applies to varX
__declspec(dllimport) class X2 {} varX;

// __declspec attribute after the class or struct keyword
// applies to user defined type
class __declspec(dllimport) X3 {};
```

## <a name="example"></a>例

識別子が、typedef である場合は、その変数名こともできません。 次の例では、C4091 が生成されます。

```
// C4091_b.cpp
// compile with: /c /W1 /WX
#define LIST 4
typedef struct _LIST {} LIST;   // C4091
```