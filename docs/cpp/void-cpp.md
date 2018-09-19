---
title: void (C++) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- void_cpp
dev_langs:
- C++
helpviewer_keywords:
- void keyword [C++]
- functions [C++], void
- pointers, void
ms.assetid: d203edba-38e6-4056-8b89-011437351057
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1aab4a8c18424fdbd52ac24444dd35a1660a714b
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46114346"
---
# <a name="void-c"></a>void (C++)

関数戻り値の型として使用すると、 **void**キーワードは、関数が値を返さないことを指定します。 関数のパラメーター リストで void を使用した場合は、関数がパラメーターを受け取らないことを示します。 ポインターの宣言で void を使用した場合は、ポインターが "汎用" であることを示します。

ポインターの型がある場合`void *`で宣言されていない任意の変数に、ポインターが指し示すことができます、 **const**または**揮発性**キーワード。 void ポインターは別の型にキャストしない限り、逆参照できません。 void ポインターは他の型のデータ ポインターに変換できます。

void ポインターは、関数を指すことはできますが、C++ のクラス メンバーを指すことはできません。

void 型の変数を宣言することはできません。

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
[基本的な型](../cpp/fundamental-types-cpp.md)