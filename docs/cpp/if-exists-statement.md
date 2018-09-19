---
title: _ _if_exists ステートメント |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- __if_exists_cpp
dev_langs:
- C++
helpviewer_keywords:
- identifiers, testing for existence
- symbols, testing for existence
- __if_exists keyword [C++]
ms.assetid: d3eb34b6-f3a9-4063-a286-b62a28c0c7fa
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4147a663ee94f09791153d9fb1697a2f66bd798c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46109213"
---
# <a name="ifexists-statement"></a>__if_exists ステートメント

**_ _If_exists**ステートメントは、指定した識別子が存在するかどうかをテストします。 ID が存在する場合、指定されたステートメント ブロックが実行されます。

## <a name="syntax"></a>構文

```
__if_exists ( identifier ) { 
statements
};
```

#### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*identifier*|存在をテストしたい識別子。|
|*ステートメント*|1 つ以上の場合に実行されるステートメント*識別子*存在します。|

## <a name="remarks"></a>Remarks

> [!CAUTION]
>  最も信頼性の高い結果を実現するために使用して、 **_ _if_exists**次の制約の下のステートメント。

- 適用、 **_ _if_exists**テンプレートではなく、唯一の単純型のステートメント。

- 適用、 **_ _if_exists**ステートメントの内部または外部クラスの識別子。 適用されません、 **_ _if_exists**ローカル変数にステートメント。

- 使用して、 **_ _if_exists**関数の本体でのみステートメント。 関数の本文の外側、 **_ _if_exists**ステートメントは、型を完全に定義のみをテストできます。

- オーバーロードされた関数をテストする場合、特定の形式のオーバーロードはテストできません。

補完する、 **_ _if_exists**ステートメントは、 [_ _if_not_exists](../cpp/if-not-exists-statement.md)ステートメント。

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
[キーワード](../cpp/keywords-cpp.md)<br/>
[__if_not_exists ステートメント](../cpp/if-not-exists-statement.md)