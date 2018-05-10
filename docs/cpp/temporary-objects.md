---
title: 一時オブジェクト |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- temporary objects
- objects [C++], temporary
ms.assetid: 4c8cec02-391e-4225-9bc6-06d150201412
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5523abd0142b8b6dc3a25beb8ca8d113cf5463bc
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="temporary-objects"></a>一時オブジェクト
場合によっては、コンパイラが一時オブジェクトを作成する必要があります。 このような一時オブジェクトが作成される理由として、次のことがあります。  
  
-   初期化する対象の参照の基になる型とは異なる型の初期化子を使用して `const` 参照を初期化するため。  
  
-   ユーザー定義型を返す関数の戻り値を格納するため。 これらの一時要素は、プログラムがオブジェクトに戻り値をコピーしない場合にのみ作成されます。 例えば:  
  
    ```  
    UDT Func1();    //  Declare a function that returns a user-defined  
                    //   type.  
  
    ...  
  
    Func1();        //  Call Func1, but discard return value.  
                    //  A temporary object is created to store the return  
                    //   value.  
    ```  
  
     戻り値は別のオブジェクトにコピーされないため、一時オブジェクトが作成されます。 一時オブジェクトが作成されるより一般的なケースは、オーバーロードされた演算子関数を呼び出す必要がある式を評価するときです。 これらのオーバーロードされた演算子関数は、多くの場合、別のオブジェクトにコピーされないユーザー定義型を返します。  
  
     式 `ComplexResult = Complex1 + Complex2 + Complex3` を考えます。 `Complex1 + Complex2` 式が評価され、結果が一時オブジェクトに格納されます。 次に、式*一時*`+ Complex3`が評価され、結果にコピーし、 `ComplexResult` (代入演算子を想定してオーバー ロードされていない)。  
  
-   キャストの結果をユーザー定義型に格納するため。 特定の型のオブジェクトがユーザー定義型に明示的に変換されるとき、新しいオブジェクトは一時オブジェクトとして作成されます。  
  
 一時オブジェクトには、作成される時点と破棄される時点とで決まる有効期間があります。 複数の一時オブジェクトを作成する式では、作成時と逆の順序で破棄が行われます。 破棄が発生するポイントを次の表に示します。  
  
### <a name="destruction-points-for-temporary-objects"></a>一時オブジェクトの破棄ポイント  
  
|一時オブジェクトが作成された理由|破棄ポイント|  
|------------------------------|-----------------------|  
|式評価の結果|式の評価の結果として作成されたすべての一時要素は、式ステートメントの最後 (セミコロンの位置)、または、`for`、`if`、`while`、`do`、および `switch` ステートメントの制御式の最後に破棄されます。|  
|`const` 参照の初期化|初期化子が初期化されている参照と同じ型の左辺値でない場合、基になるオブジェクト型の一時オブジェクトが作成され、初期化式で初期化されます。 この一時オブジェクトは、バインド先の参照オブジェクトが破棄された直後に破棄されます。|  
  
