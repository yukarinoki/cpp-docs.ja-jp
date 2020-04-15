---
title: __if_exists ステートメント
ms.date: 11/04/2016
f1_keywords:
- __if_exists_cpp
helpviewer_keywords:
- identifiers, testing for existence
- symbols, testing for existence
- __if_exists keyword [C++]
ms.assetid: d3eb34b6-f3a9-4063-a286-b62a28c0c7fa
ms.openlocfilehash: 609d576c6ab3eddca569ed4f19a4024b47b6a1d2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374152"
---
# <a name="__if_exists-statement"></a>__if_exists ステートメント

**__if_exists**ステートメントは、指定された識別子が存在するかどうかをテストします。 ID が存在する場合、指定されたステートメント ブロックが実行されます。

## <a name="syntax"></a>構文

```
__if_exists ( identifier ) {
statements
};
```

#### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*識別子*|存在をテストしたい識別子。|
|*ステートメント*|*識別子*が存在する場合に実行する 1 つ以上のステートメント。|

## <a name="remarks"></a>解説

> [!CAUTION]
> 最も信頼性の高い結果を得るには、次の制約の下で **__if_exists**ステートメントを使用します。

- **__if_exists**ステートメントは、テンプレートではなく単純型にのみ適用します。

- クラスの内部または外部の識別子に **__if_exists**ステートメントを適用します。 ローカル変数に **__if_exists**ステートメントを適用しないでください。

- **__if_exists**ステートメントは、関数の本体でのみ使用してください。 関数の本体の外側では **、__if_exists**ステートメントは完全に定義された型のみをテストできます。

- オーバーロードされた関数をテストする場合、特定の形式のオーバーロードはテストできません。

**__if_exists**ステートメントの補数は[、__if_not_exists](../cpp/if-not-exists-statement.md)ステートメントです。

## <a name="example"></a>例

この例ではテンプレートを使用していますが、これは推奨されません。

```cpp
// the__if_exists_statement.cpp
// compile with: /EHsc
#include <iostream>

template<typename T>
class X : public T {
public:
   void Dump() {
      std::cout << "In X<T>::Dump()" << std::endl;

      __if_exists(T::Dump) {
         T::Dump();
      }

      __if_not_exists(T::Dump) {
         std::cout << "T::Dump does not exist" << std::endl;
      }
   }
};

class A {
public:
   void Dump() {
      std::cout << "In A::Dump()" << std::endl;
   }
};

class B {};

bool g_bFlag = true;

class C {
public:
   void f(int);
   void f(double);
};

int main() {
   X<A> x1;
   X<B> x2;

   x1.Dump();
   x2.Dump();

   __if_exists(::g_bFlag) {
      std::cout << "g_bFlag = " << g_bFlag << std::endl;
   }

   __if_exists(C::f) {
      std::cout << "C::f exists" << std::endl;
   }

   return 0;
}
```

## <a name="output"></a>出力

```Output
In X<T>::Dump()
In A::Dump()
In X<T>::Dump()
T::Dump does not exist
g_bFlag = 1
C::f exists
```

## <a name="see-also"></a>関連項目

[選択ステートメント](../cpp/selection-statements-cpp.md)<br/>
[Keywords](../cpp/keywords-cpp.md)<br/>
[__if_not_existsステートメント](../cpp/if-not-exists-statement.md)
