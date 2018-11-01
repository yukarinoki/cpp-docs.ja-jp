---
title: marshal_context クラス
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- marshal_context
helpviewer_keywords:
- marshal_context class [C++]
ms.assetid: 241b0cf6-4ca4-4812-aaee-d671c11dc034
ms.openlocfilehash: 0e25aee0996b0cd16ca92566da22d377b762d7bc
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50594533"
---
# <a name="marshalcontext-class"></a>marshal_context クラス

このクラスは、ネイティブおよびマネージ環境間でデータを変換します。

## <a name="syntax"></a>構文

```
class marshal_context
```

## <a name="remarks"></a>Remarks

使用して、`marshal_context`コンテキストを必要とするデータ変換のクラス。 参照してください[c++ Overview of Marshaling](../dotnet/overview-of-marshaling-in-cpp.md)詳細については、どの変換コンテキストが必要し、マーシャ リングするファイルが含まれる必要があります。 コンテキストを使用する場合にマーシャ リングの結果は有効期限のみ、`marshal_context`オブジェクトは破棄されます。 結果を保持するには、データをコピーする必要があります。

同じ`marshal_context`複数のデータ変換に使用できます。 この方法でコンテキストを再利用しても、以前のマーシャ リングの呼び出しの結果は影響しません。

## <a name="requirements"></a>必要条件

**ヘッダー ファイル:** \<msclr\marshal.h >、 \<msclr\marshal_windows.h >、 \<msclr\marshal_cppstd.h >、または\<msclr\marshal_atl.h >

**Namespace:** msclr::interop

## <a name="see-also"></a>関連項目

[C++ におけるマーシャリングの概要](../dotnet/overview-of-marshaling-in-cpp.md)<br/>
[marshal_as](../dotnet/marshal-as.md)