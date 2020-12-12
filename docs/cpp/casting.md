---
description: 詳細については、「キャスト」を参照してください。
title: キャスト
ms.date: 11/19/2018
helpviewer_keywords:
- casting [C++]
- coercion [C++]
- virtual functions [C++], in derived classes [C++]
- static cast operator
- dynamic cast operator
- polymorphic classes [C++]
- classes [C++], polymorphism
ms.assetid: 3dbeb06e-2f4b-4693-832d-624bc8ec95de
ms.openlocfilehash: 0850b20db0e3f951414ba2b1d480cdcf43fb971f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97308641"
---
# <a name="casting"></a>キャスト

C++ 言語では、仮想関数を含む基底クラスからクラスが派生している場合は、その基底クラスの型へのポインターを使用して、派生クラス オブジェクトに存在する仮想関数の実装を呼び出すことができると規定されています。 仮想関数を含むクラスは、"ポリモーフィックなクラス" と呼ばれます。

派生クラスには派生元のすべての基底クラスの定義が完全に含まれるため、ポインターをクラスの階層構造の任意の基底クラスにキャストしても、安全です。 基底クラスへのポインターの場合は、下の階層にポインターを安全にキャストできる場合もあります。 ポイントされているオブジェクトが実際に基底クラスから派生した型である場合は、安全です。 この場合、実際のオブジェクトは "完全なオブジェクト" と呼ばれます。 基底クラスへのポインターは完全なオブジェクトの "サブオブジェクト" をポイントすると表現されます。 たとえば、次の図に示すクラスの階層構造を考えます。

![クラスの階層構造](../cpp/media/vc38zz1.gif "クラスの階層構造") <br/>
クラスの階層構造

`C` 型のオブジェクトは、次の図に示すように視覚化できます。

![サブ&#45;オブジェクト B と A のクラス C](../cpp/media/vc38zz2.gif "サブ&#45;オブジェクト B と A のクラス C") <br/>
B サブオブジェクトと A サブオブジェクトを持つクラス C

`C` クラスのインスタンスには、`B` サブオブジェクトと `A` サブオブジェクトがあります。 `C` サブオブジェクトと `A` サブオブジェクトを含む `B` のインスタンスは、「完全なオブジェクト」です。

実行時の型情報を使用すると、ポインターが実際に完全なオブジェクトをポイントしていて、階層内の別のオブジェクトをポイントするように安全にキャストできるかどうかを調べることができます。 [Dynamic_cast](../cpp/dynamic-cast-operator.md)演算子を使用すると、これらの種類のキャストを行うことができます。 また、操作を安全にするために必要なランタイム チェックも実行します。

非ポリモーフィック型の変換では、 [static_cast](../cpp/static-cast-operator.md) 演算子を使用できます (このトピックでは、静的キャスト変換と動的キャスト変換の違いと、それぞれの使用に適した場合の違いについて説明します)。

このセクションは、次のトピックで構成されています。

- [キャスト演算子](../cpp/casting-operators.md)

- [実行時の型情報](../cpp/run-time-type-information.md)

## <a name="see-also"></a>関連項目

[式](../cpp/expressions-cpp.md)
