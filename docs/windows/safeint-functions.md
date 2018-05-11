---
title: SafeInt 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- functions, SafeInt
ms.assetid: fdc208e5-5d8a-41a9-8271-567fd438958d
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 97edd25abca3c9e80a35745165eedc93cc13a9b9
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="safeint-functions"></a>SafeInt 関数
SafeInt ライブラリには、インスタンスを作成せずに使用できるいくつかの関数が用意されています、 [SafeInt クラス](../windows/safeint-class.md)です。 整数オーバーフローから単一の数値演算を保護する場合は、これらの関数を使用することができます。 作成する必要があります複数の数値演算を保護する場合は、`SafeInt`オブジェクト。 作成する方が効率的である`SafeInt`にこれらの関数を複数回使用よりもオブジェクトです。  
  
 これらの関数を使用すると、比較または最初に、同じ型に変換することがなく 2 つの異なる型のパラメーターの算術演算を実行できます。  
  
 これらの関数の各テンプレートの 2 つの種類には:`T`と`U`です。 これらの型は、ブール値を文字、または整数型にします。 整数型の符号付きまたは符号なしでき、8 ビットから 64 ビットの任意のサイズ。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
|関数|説明|  
|--------------|-----------------|  
|[SafeAdd](../windows/safeadd.md)|2 つの数値を追加し、オーバーフローが生じないようにします。|  
|[SafeCast](../windows/safecast.md)|別の型パラメーターの型にキャストします。|  
|[SafeDivide](../windows/safedivide.md)|2 つの数値を除算し、ゼロ除算から保護します。|  
|[SafeEquals](../windows/safeequals.md)、 [SafeGreaterThan](../windows/safegreaterthan.md)、 [SafeGreaterThanEquals](../windows/safegreaterthanequals.md)、 [SafeLessThan](../windows/safelessthan.md)、 [SafeLessThanEquals](../windows/safelessthanequals.md)、 [SafeNotEquals](../windows/safenotequals.md)|2 つの数値を比較します。 これらの関数を使用すると、その型を変更することがなく 2 つの異なる型の数値を比較できます。|  
|[SafeModulus](../windows/safemodulus.md)|2 つの数値に対して剰余演算を実行します。|  
|[SafeMultiply](../windows/safemultiply.md)|2 つの数値を乗算し、オーバーフローを保護できます。|  
|[SafeSubtract](../windows/safesubtract.md)|2 つの数値を減算し、オーバーフローが生じないようにします。|  
  
## <a name="related-sections"></a>関連項目  
  
|セクション|説明|  
|-------------|-----------------|  
|[SafeInt クラス](../windows/safeint-class.md)|`SafeInt` クラス|  
|[SafeIntException クラス](../windows/safeintexception-class.md)|SafeInt ライブラリに固有の例外クラスです。|