---
title: marshal_context::marshal_context
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- msclr::interop::marshal_context::marshal_context
- marshal_context::marshal_context
- msclr.interop.marshal_context.marshal_context
- marshal_context.marshal_context
helpviewer_keywords:
- marshal_context class [C++], operations
ms.assetid: 5f08c895-60b0-4f72-97ff-7ae37c68e853
ms.openlocfilehash: a1a62c47450224aa2bcacde75038adf7a8cfbb9d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50532588"
---
# <a name="marshalcontextmarshalcontext"></a>marshal_context::marshal_context

構築、`marshal_context`マネージとネイティブのデータ型間のデータ変換に使用するオブジェクト。

## <a name="syntax"></a>構文

```
marshal_context();
```

## <a name="remarks"></a>Remarks

一部のデータ変換には、マーシャ リング コンテキストが必要です。 参照してください[c++ Overview of Marshaling](../dotnet/overview-of-marshaling-in-cpp.md)詳細については、コンテキストが必要にどの翻訳とマーシャ リングするファイルは、アプリケーションに含める必要があります。

## <a name="example"></a>例

例をご覧ください[marshal_context::marshal_as](../dotnet/marshal-context-marshal-as.md)します。

## <a name="requirements"></a>必要条件

**ヘッダー ファイル:** \<msclr\marshal.h >、 \<msclr\marshal_windows.h >、 \<msclr\marshal_cppstd.h >、または\<msclr\marshal_atl.h >

**Namespace:** msclr::interop

## <a name="see-also"></a>関連項目

[C++ におけるマーシャリングの概要](../dotnet/overview-of-marshaling-in-cpp.md)<br/>
[marshal_as](../dotnet/marshal-as.md)<br/>
[marshal_context クラス](../dotnet/marshal-context-class.md)