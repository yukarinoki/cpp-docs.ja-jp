---
title: オーバーライド指定子 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- override Identifier
ms.assetid: b286fb46-9374-4ad8-b2e7-4607119b6133
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 596580bdd4cb7c5610e7cb68341fba4a3da981ac
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46106143"
---
# <a name="override-specifier"></a>override 指定子

使用することができます、**オーバーライド**キーワードを基底クラスで仮想関数をオーバーライドする関数のメンバーを指定します。

## <a name="syntax"></a>構文

```
function-declaration override;
```

## <a name="remarks"></a>Remarks

**オーバーライド**状況依存であり、つまり場合にのみ特別なは、メンバー関数宣言の後に使用されます。 それ以外の場合は、予約済みキーワード。

## <a name="example"></a>例

使用**オーバーライド**コードでの誤った継承動作を防ぐためです。 次の例を使用せず、where を示しています**オーバーライド**、派生クラスのメンバー関数の動作が意図されていません。 このコードに対してコンパイラ エラーは発生しません。

```cpp
class BaseClass
{
    virtual void funcA();
    virtual void funcB() const;
    virtual void funcC(int = 0);
    void funcD();
};

class DerivedClass: public BaseClass
{
    virtual void funcA(); // ok, works as intended

    virtual void funcB(); // DerivedClass::funcB() is non-const, so it does not
                          // override BaseClass::funcB() const and it is a new member function

    virtual void funcC(double = 0.0); // DerivedClass::funcC(double) has a different
                                      // parameter type than BaseClass::funcC(int), so
                                      // DerivedClass::funcC(double) is a new member function
};
```

使用すると**オーバーライド**コンパイラは自動的に新しいメンバー関数を作成するのではなくエラーを生成します。

```cpp
class BaseClass
{
    virtual void funcA();
    virtual void funcB() const;
    virtual void funcC(int = 0);
    void funcD();
};

class DerivedClass: public BaseClass
{
    virtual void funcA() override; // ok

    virtual void funcB() override; // compiler error: DerivedClass::funcB() does not
                                   // override BaseClass::funcB() const

    virtual void funcC( double = 0.0 ) override; // compiler error:
                                                 // DerivedClass::funcC(double) does not
                                                 // override BaseClass::funcC(int)

    void funcD() override; // compiler error: DerivedClass::funcD() does not
                           // override the non-virtual BaseClass::funcD()
};
```

関数をオーバーライドできないこととクラスを継承できないことを指定するには、使用、[最終的な](../cpp/final-specifier.md)キーワード。

## <a name="see-also"></a>関連項目

[final 指定子](../cpp/final-specifier.md)<br/>
[キーワード](../cpp/keywords-cpp.md)