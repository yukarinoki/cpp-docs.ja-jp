---
title: final 指定子
ms.date: 11/04/2016
f1_keywords:
- final_CPP
helpviewer_keywords:
- final Identifier
ms.assetid: 649866d0-79d4-449f-ab74-f84b911b79a3
ms.openlocfilehash: 93e8d9b0b445d1120ec15911eb763ae1d7d2d359
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80188659"
---
# <a name="final-specifier"></a>final 指定子

**Final**キーワードを使用して、派生クラスでオーバーライドできない仮想関数を指定できます。 また、このキーワードは、継承できないクラスの指定にも使用できます。

## <a name="syntax"></a>構文

```
function-declaration final;
class class-name final base-classes
```

## <a name="remarks"></a>解説

**final**は状況に依存しており、関数宣言またはクラス名の後に使用される場合にのみ、特別な意味を持ちます。それ以外の場合は、予約済みのキーワードではありません。

**Final**をクラス宣言で使用した場合、`base-classes` は宣言の省略可能な部分です。

## <a name="example"></a>例

次の例では、 **final**キーワードを使用して、仮想関数をオーバーライドできないことを指定します。

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

メンバー関数をオーバーライドできるように指定する方法については、「 [Override 指定子](../cpp/override-specifier.md)」を参照してください。

次の例では、 **final**キーワードを使用して、クラスを継承できないことを指定しています。

```cpp
class BaseClass final
{
};

class DerivedClass: public BaseClass // compiler error: BaseClass is
                                     // marked as non-inheritable
{
};
```

## <a name="see-also"></a>参照

[キーワード](../cpp/keywords-cpp.md)<br/>
[override 指定子](../cpp/override-specifier.md)
