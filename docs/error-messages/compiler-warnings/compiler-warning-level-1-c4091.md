---
title: コンパイラの警告 (レベル 1) C4091
ms.date: 11/04/2016
f1_keywords:
- C4091
helpviewer_keywords:
- C4091
ms.assetid: 3a404967-ab42-49b0-b324-fd7ba1859d78
ms.openlocfilehash: 87432a74dfe7c09a52f436d4e91b3f70eb66856b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62410448"
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