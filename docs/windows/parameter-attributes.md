---
title: パラメーターの属性 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- attributes [C++], parameter attributes
- parameter attributes
ms.assetid: 024c2dd5-49d7-4ced-a17a-c56c1bc485b6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f96c5e3bcdd48f4fe3144b0e8885e82c2093a1d3
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2018
ms.locfileid: "39608846"
---
# <a name="parameter-attributes"></a>パラメーター属性
次の属性は、クラスまたはインターフェイスのメソッドのパラメーターに適用されます。  
  
|属性|説明|  
|---------------|-----------------|  
|[custom](../windows/custom-cpp.md)|独自の属性を定義できます。|  
|[defaultvalue](../windows/defaultvalue.md)|型指定された省略可能なパラメーターの既定値を指定をできます。|  
|[first_is](../windows/first-is.md)|転送する最初の配列要素のインデックスを指定します。|  
|[iid_is](../windows/iid-is.md)|転送する最初の配列要素のインデックスを指定します。|  
|[immediatebind](../windows/immediatebind.md)|データ バインド オブジェクトのプロパティに対するすべての変更のデータベースに直ちに通知されることを示します。|  
|[in](../windows/in-cpp.md)|呼び出し元のプロシージャから呼び出されたプロシージャに渡されるパラメーターがあることを示します。|  
|[last_is](../windows/last-is.md)|転送する最後の配列要素のインデックスを指定します。|  
|[lcid](../windows/lcid.md)|ロケール識別子を関数に渡すことができます。|  
|[length_is](../windows/length-is.md)|転送する配列要素の数を指定します。|  
|[max_is](../windows/max-is.md)|有効な配列のインデックスの最大値を指定します。|  
|[省略可能](../windows/optional-cpp.md)|メンバー関数のオプション パラメーターを指定します。|  
|[out](../windows/out-cpp.md)|呼び出されたプロシージャから呼び出したプロシージャ (サーバーからクライアント) に返されるポインター パラメーターを示します。|  
|[range](../windows/range-cpp.md)|引数または値を持つが実行時に設定されているフィールドに使用できる値の範囲を指定します。|  
|[ref](../windows/ref-cpp.md)|参照ポインターを識別します。|  
|[retval](../windows/retval.md)|メンバーの戻り値を受け取るパラメーターを指定します。|  
|[satype](../windows/satype.md)|データ型を指定します、`SAFEARRAY`構造体。|  
|[size_is](../windows/size-is.md)|メモリのサイズがサイズのポインターに割り当てられた、サイズのポインター、および 1 次元または多次元配列へのポインターのサイズを指定します。|  
|[unique](../windows/unique-cpp.md)|一意のポインターを指定します。|  
  
## <a name="see-also"></a>関連項目  
 [使用法別の属性](../windows/attributes-by-usage.md)