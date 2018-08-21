---
title: SafeInt 関数 |Microsoft Docs
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
ms.openlocfilehash: b8a0475b5d3ba9053cd5d2df5ffd99ce9292ba8e
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2018
ms.locfileid: "39603456"
---
# <a name="safeint-functions"></a>SafeInt 関数
SafeInt ライブラリのインスタンスを作成せずに使用できるいくつかの機能を提供する、 [SafeInt クラス](../windows/safeint-class.md)します。 単一の数値演算を整数のオーバーフローから保護する場合は、これらの関数を使用できます。 複数の数値演算を保護する場合は、作成する必要があります**SafeInt**オブジェクト。 作成する方が効率的です**SafeInt**にこれらの関数を複数回使用よりもオブジェクトです。  
  
 これらの関数を使用すると、比較または最初に、同じ型に変換することがなく 2 つの異なる型のパラメーターの算術演算を実行できます。  
  
 これらの各関数は、テンプレートの 2 つの種類:`T`と`U`します。 これらの型には、ブール値、文字、または整数型ができます。 整数型の符号付きまたは符号なしでき、あらゆるサイズを 8 ビットから 64 ビット。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
|関数|説明|  
|--------------|-----------------|  
|[SafeAdd](../windows/safeadd.md)|2 つの数値を追加し、オーバーフローから保護します。|  
|[SafeCast](../windows/safecast.md)|別の型パラメーターの型にキャストします。|  
|[SafeDivide](../windows/safedivide.md)|2 つの数値を除算し、0 で除算することを防ぎます。|  
|[SafeEquals](../windows/safeequals.md)、 [SafeGreaterThan](../windows/safegreaterthan.md)、 [SafeGreaterThanEquals](../windows/safegreaterthanequals.md)、 [SafeLessThan](../windows/safelessthan.md)、 [SafeLessThanEquals](../windows/safelessthanequals.md)、 [SafeNotEquals](../windows/safenotequals.md)|2 つの数値を比較します。 これらの関数を使用すると、その型を変更することがなく 2 つの異なる型の数値を比較できます。|  
|[SafeModulus](../windows/safemodulus.md)|2 つの数値に対して剰余演算を実行します。|  
|[SafeMultiply](../windows/safemultiply.md)|2 つの数値を乗算し、オーバーフローを保護します。|  
|[SafeSubtract](../windows/safesubtract.md)|2 つの数値を減算し、オーバーフローから保護します。|  
  
## <a name="related-sections"></a>関連項目  
  
|セクション|説明|  
|-------------|-----------------|  
|[SafeInt クラス](../windows/safeint-class.md)|**SafeInt**クラス。|  
|[SafeIntException クラス](../windows/safeintexception-class.md)|SafeInt ライブラリに固有の例外クラスです。|