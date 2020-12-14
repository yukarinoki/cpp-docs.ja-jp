---
description: '詳細情報: コンパイラの警告 (レベル 1) C4743'
title: コンパイラの警告 (レベル 1) C4743
ms.date: 05/13/2019
f1_keywords:
- C4743
helpviewer_keywords:
- C4743
ms.assetid: 2ee76ea3-77f3-4c2f-9a57-0751823c89fd
ms.openlocfilehash: a8c8bcd4ef0e4d7084da34e033be4194da11727f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97228483"
---
# <a name="compiler-warning-level-1-c4743"></a>コンパイラの警告 (レベル 1) C4743

'*type*' のサイズが '*file1*' と '*file2*' で異なっています: *number* と *number* bytes

2つのファイルで参照または定義されている外部変数は、これらのファイル内で異なる型を持っています。また、コンパイラは、 *file1* の変数のサイズが *file2* の変数のサイズと異なることを判断しました。

## <a name="remarks"></a>解説

この警告が C++ に対して生成される場合は、重要なケースがあります。 2つの異なるファイルで同じ名前を持つ同じ型を宣言する場合、これらの宣言に仮想関数が含まれている場合、および宣言が同じでない場合、コンパイラは仮想関数テーブルに対して警告 C4744 を出力できます。 この警告が発生するのは、同じ型に対して2つの異なるサイズの仮想関数テーブルが存在し、リンカーがそのうちの1つを選択して実行可能ファイルに組み込む必要があるためです。  プログラムが間違った仮想関数を呼び出す可能性があります。

この警告を解決するには、同じ型定義を使用するか、型または変数に別の名前を使用します。

## <a name="example"></a>例

次の例では、C4743 が生成されます。 これをコンパイルするには、両方のファイルを同じフォルダーに配置し、を実行します。  

```cmd
cl /EHsc /W1 /GL /O2 C4743a.cpp C4743b.cpp
```

```cpp
// C4743a.cpp
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

```cpp
// C4743b.cpp
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
