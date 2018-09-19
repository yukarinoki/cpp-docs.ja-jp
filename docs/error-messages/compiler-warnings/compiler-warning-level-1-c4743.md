---
title: コンパイラの警告 (レベル 1) C4743 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4743
dev_langs:
- C++
helpviewer_keywords:
- C4743
ms.assetid: 2ee76ea3-77f3-4c2f-9a57-0751823c89fd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6387c1b4b02902fdb3eec468c753ff08de6e91f7
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46111161"
---
# <a name="compiler-warning-level-1-c4743"></a>コンパイラの警告 (レベル 1) C4743

'*型*'別のサイズが、'*file1*'と'*file2*':*数*と*数*バイト

または、参照される 2 つのファイルで定義されている外部変数が、それらのファイルのさまざまな種類と、コンパイラが決定される変数のサイズ*file1*内の変数のサイズと異なります*file2*.

C++ の場合、この警告を出力できる場合に重要な場合は。 宣言が異なる場合、それらの宣言には、仮想関数が含まれている場合に 2 つの異なるファイルで同じ名前を持つ同じ型を宣言する場合、コンパイラは警告 C4744 仮想関数テーブルを生成できます。 警告が発生したは、同じ型の 2 つの異なるサイズの仮想関数テーブルがある、リンカーは、1 つを実行可能ファイルに組み込むことを選択する必要があります。  これが間違った仮想関数を呼び出して、プログラムで発生することができます可能性があります。

この警告を解決するには、同じ種類の定義を使用するか型または変数に対して異なる名前を使用します。

## <a name="example"></a>例

このサンプルには、型の 1 つの定義が含まれています。

```
// C4743a.cpp
// compile with: /c
class C {
public:
    virtual void f1(void);
    virtual void f2(void);
    virtual void f3(void);
};

void C::f1(void) {}
void C::f2(void) {}
void C::f3(void) {}
C q;
```

## <a name="example"></a>例

次の例では、C4743 が生成されます。

```
// C4743b.cpp
// compile with: C4743a.cpp /W1 /GL /O2
// C4743 expected
class C {
public:
    virtual void f1(void);
    virtual void f2(void);
    virtual void f3(void);
    virtual void f4(void);
    virtual void f5(void);
};

void C::f4(void) {}
void C::f5(void) {}
C x;

int main() {}
```