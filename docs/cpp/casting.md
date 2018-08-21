---
title: キャスト |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- casting [C++]
- coercion [C++]
- virtual functions [C++], in derived classes [C++]
- static cast operator
- dynamic cast operator
- polymorphic classes [C++]
- classes [C++], polymorphism
ms.assetid: 3dbeb06e-2f4b-4693-832d-624bc8ec95de
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9c7dfe18c65fcde7cbfa0ea2121234f2896a2723
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/01/2018
ms.locfileid: "39405020"
---
# <a name="casting"></a>キャスト
C++ 言語では、仮想関数を含む基底クラスからクラスが派生している場合は、その基底クラスの型へのポインターを使用して、派生クラス オブジェクトに存在する仮想関数の実装を呼び出すことができると規定されています。 仮想関数を含むクラスは、"ポリモーフィックなクラス" と呼ばれます。  
  
 派生クラスには派生元のすべての基底クラスの定義が完全に含まれるため、ポインターをクラスの階層構造の任意の基底クラスにキャストしても、安全です。 基底クラスへのポインターの場合は、下の階層にポインターを安全にキャストできる場合もあります。 ポイントされているオブジェクトが実際に基底クラスから派生した型である場合は、安全です。 この場合、実際のオブジェクトは "完全なオブジェクト" と呼ばれます。 基底クラスへのポインターは完全なオブジェクトの "サブオブジェクト" をポイントすると表現されます。 たとえば、次の図に示すクラスの階層構造を考えます。  
  
 ![クラス階層](../cpp/media/vc38zz1.gif "vc38ZZ1")  
クラスの階層構造  
  
 `C` 型のオブジェクトは、次の図に示すように視覚化できます。  
  
 ![Sub を持つクラス C&#45;オブジェクト B と A](../cpp/media/vc38zz2.gif "vc38ZZ2")  
B サブオブジェクトと A サブオブジェクトを持つクラス C  
  
 `C` クラスのインスタンスには、`B` サブオブジェクトと `A` サブオブジェクトがあります。 `C` サブオブジェクトと `A` サブオブジェクトを含む `B` のインスタンスは、「完全なオブジェクト」です。  
  
 実行時の型情報を使用すると、ポインターが実際に完全なオブジェクトをポイントしていて、階層内の別のオブジェクトをポイントするように安全にキャストできるかどうかを調べることができます。 [Dynamic_cast](../cpp/dynamic-cast-operator.md)演算子は、これらの型のキャストを使用できます。 また、操作を安全にするために必要なランタイム チェックも実行します。  
  
 非ポリモーフィックな型の変換で使用することができます、 [static_cast](../cpp/static-cast-operator.md)演算子 (このトピックには、各を使用する適切なタイミングと、静的および動的なキャスト変換の間の差がについて説明します)。  
  
 ここでは、次のトピックについて説明します。  
  
-   [キャスト演算子](../cpp/casting-operators.md)  
  
-   [実行時の型情報](../cpp/run-time-type-information.md)  
  
## <a name="see-also"></a>関連項目  
 [式](../cpp/expressions-cpp.md)