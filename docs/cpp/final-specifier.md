---
title: final 指定子
ms.date: 11/04/2016
f1_keywords:
- final_CPP
helpviewer_keywords:
- final Identifier
ms.assetid: 649866d0-79d4-449f-ab74-f84b911b79a3
ms.openlocfilehash: c6400c8060664713fdd004a5aa9536e0617bc0c8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50588085"
---
# <a name="final-specifier"></a>final 指定子

使用することができます、**最終的な**キーワードを派生クラスでオーバーライドできない仮想関数を指定します。 また、このキーワードは、継承できないクラスの指定にも使用できます。

## <a name="syntax"></a>構文

```
function-declaration final;
class class-name final base-classes
```

## <a name="remarks"></a>Remarks

**最終的な**は状況依存と予約済みキーワードではありません関数宣言の後に使用されますか、クラスの名前。 それ以外の場合、だけに特別な意味を持ちます。

ときに**最終的な**クラスの宣言で使用される、`base-classes`宣言の省略可能な部分です。

## <a name="example"></a>例

次の例では、**最終的な**仮想関数をオーバーライドできないことを指定するキーワード。

```cpp
class BaseClass
{
    virtual void func() final;
};

class DerivedClass: public BaseClass
{
    virtual void func(); // compiler error: attempting to
                         // override a final function
};
```

メンバー関数をオーバーライドできることを指定する方法については、[オーバーライド指定子](../cpp/override-specifier.md)を参照してください。

次の例では、**最終**クラスを継承できないことを指定するキーワード。

```cpp
class BaseClass final
{
};

class DerivedClass: public BaseClass // compiler error: BaseClass is
                                     // marked as non-inheritable
{
};
```

## <a name="see-also"></a>関連項目

[キーワード](../cpp/keywords-cpp.md)<br/>
[override 指定子](../cpp/override-specifier.md)