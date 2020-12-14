---
description: '詳細情報: final 指定子'
title: final 指定子
ms.date: 11/04/2016
f1_keywords:
- final_CPP
helpviewer_keywords:
- final Identifier
ms.assetid: 649866d0-79d4-449f-ab74-f84b911b79a3
ms.openlocfilehash: 5fd6ee3c23a455c4316593cc089c26c34477709d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97242614"
---
# <a name="final-specifier"></a>final 指定子

**Final** キーワードを使用して、派生クラスでオーバーライドできない仮想関数を指定できます。 また、このキーワードは、継承できないクラスの指定にも使用できます。

## <a name="syntax"></a>構文

```
function-declaration final;
class class-name final base-classes
```

## <a name="remarks"></a>解説

**final** は状況に依存しており、関数宣言またはクラス名の後に使用される場合にのみ、特別な意味を持ちます。それ以外の場合は、予約済みのキーワードではありません。

**Final** がクラス宣言で使用される場合、 `base-classes` は宣言の省略可能な部分です。

## <a name="example"></a>例

次の例では、 **final** キーワードを使用して、仮想関数をオーバーライドできないことを指定します。

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

次の例では、 **final** キーワードを使用して、クラスを継承できないことを指定しています。

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
[オーバーライド指定子](../cpp/override-specifier.md)
