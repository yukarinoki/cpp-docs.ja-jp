---
title: marshal_context クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- marshal_context
dev_langs:
- C++
helpviewer_keywords:
- marshal_context class [C++]
ms.assetid: 241b0cf6-4ca4-4812-aaee-d671c11dc034
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 6bf712e960cbf96ccef6c3a3e4efebdad9045818
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33136995"
---
# <a name="marshalcontext-class"></a>marshal_context クラス
このクラスは、ネイティブおよびマネージ環境間でデータを変換します。  
  
## <a name="syntax"></a>構文  
  
```  
class marshal_context  
```  
  
## <a name="remarks"></a>コメント  
 使用して、`marshal_context`コンテキストを必要とするデータ変換のクラスです。 参照してください[概要の C++ におけるマーシャ リング](../dotnet/overview-of-marshaling-in-cpp.md)詳細については、どの変換コンテキストが必要にあり、マーシャ リング ファイルを含める。 マーシャ リング コンテキストを使用する場合の結果の有効期限のみ、`marshal_context`オブジェクトは破棄されます。 結果を保持するには、データをコピーする必要があります。  
  
 同じ`marshal_context`複数のデータ変換に使用できます。 この方法でコンテキストを再利用しても、以前のマーシャ リングの呼び出しからの結果に影響はありません。  
  
## <a name="requirements"></a>要件  
 **ヘッダー ファイル:** \<msclr\marshal.h >、 \<msclr\marshal_windows.h >、 \<msclr\marshal_cppstd.h >、または\<msclr\marshal_atl.h >  
  
 **Namespace:** msclr::interop  
  
## <a name="see-also"></a>関連項目  
 [C++ におけるマーシャ リングの概要](../dotnet/overview-of-marshaling-in-cpp.md)   
 [marshal_as](../dotnet/marshal-as.md)