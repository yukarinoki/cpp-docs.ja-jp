---
description: ': Void (C++) についての詳細情報'
title: void (C++)
ms.date: 11/04/2016
f1_keywords:
- void_cpp
helpviewer_keywords:
- void keyword [C++]
- functions [C++], void
- pointers, void
ms.assetid: d203edba-38e6-4056-8b89-011437351057
ms.openlocfilehash: e49dfa03e289cdbace50a24cf6854d25c51b3426
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97213352"
---
# <a name="void-c"></a>void (C++)

関数の戻り値の型として使用する場合、キーワードは、 **`void`** 関数が値を返さないことを指定します。 関数のパラメーターリストで使用する場合は、 **`void`** 関数がパラメーターを受け取らないことを指定します。 ポインターの宣言で使用する場合、 **`void`** ポインターが "universal" であることを指定します。

ポインターの型が **void _ の場合、ポインターは、_ \* `const` またはキーワードで宣言されて *いない任意の変数を指すことができ*** **`volatile`** ます。 別の型にキャストしない限り、**void \** _ ポインターを逆参照することはできません。 _*Void \**_ ポインターは、他の任意の型のデータポインターに変換できます。

_ *`void`* * ポインターは関数を指すことができますが、C++ のクラスメンバーを指すことはできません。

型の変数を宣言することはできません **`void`** 。

## <a name="example"></a>例

```cpp
// void.cpp
void vobject;   // C2182
void *pv;   // okay
int *pint; int i;
int main() {
   pv = &i;
   // Cast optional in C required in C++
   pint = (int *)pv;
}
```

## <a name="see-also"></a>関連項目

[キーワード](../cpp/keywords-cpp.md)<br/>
[組み込み型](../cpp/fundamental-types-cpp.md)
