---
title: override 指定子
ms.date: 11/04/2016
helpviewer_keywords:
- override Identifier
ms.assetid: b286fb46-9374-4ad8-b2e7-4607119b6133
ms.openlocfilehash: 82837ae34ab786e607df54038493b14350574a15
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80188481"
---
# <a name="override-specifier"></a>override 指定子

**Override**キーワードを使用して、基底クラスの仮想関数をオーバーライドするメンバー関数を指定できます。

## <a name="syntax"></a>構文

```
function-declaration override;
```

## <a name="remarks"></a>解説

**オーバーライド**は状況に依存し、メンバー関数の宣言の後に使用される場合にのみ、特別な意味を持ちます。それ以外の場合は、予約済みのキーワードではありません。

## <a name="example"></a>例

**オーバーライド**を使用すると、コードの意図しない継承動作を防ぐことができます。 次の例では、 **override**を使用しない場合、派生クラスのメンバー関数の動作が意図していない可能性があることを示しています。 このコードに対してコンパイラ エラーは発生しません。

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

**Override**を使用すると、コンパイラは、新しいメンバー関数をサイレントで作成するのではなく、エラーを生成します。

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

関数をオーバーライドできず、そのクラスを継承できないように指定するには、 [final](../cpp/final-specifier.md)キーワードを使用します。

## <a name="see-also"></a>参照

[final 指定子](../cpp/final-specifier.md)<br/>
[キーワード](../cpp/keywords-cpp.md)
