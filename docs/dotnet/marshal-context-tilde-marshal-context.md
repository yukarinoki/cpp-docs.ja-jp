---
title: marshal_context::~marshal_context
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- marshal_context::~marshal_context
- msclr.interop.marshal_context.~marshal_context
- marshal_context.~marshal_context
- msclr::interop::marshal_context::~marshal_context
- ~marshal_context
helpviewer_keywords:
- marshal_context class [C++], operations
ms.assetid: 34c41b38-4c33-4f61-b74e-831ac46b4ab5
ms.openlocfilehash: 3bf16ab2dde4047fb845cd700821d097f733a4d2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50528220"
---
# <a name="marshalcontextmarshalcontext"></a>marshal_context::~marshal_context

`marshal_context` オブジェクトを破棄します。

## <a name="syntax"></a>構文

```
~marshal_context();
```

## <a name="remarks"></a>Remarks

一部のデータ変換には、マーシャ リング コンテキストが必要です。 参照してください[c++ Overview of Marshaling](../dotnet/overview-of-marshaling-in-cpp.md)詳細については、コンテキストが必要にどの翻訳とマーシャ リングするファイルは、アプリケーションに含める必要があります。

削除、`marshal_context`オブジェクトがそのコンテキストによって変換されたデータが無効になります。 後にデータを保持する場合、`marshal_context`オブジェクトが破棄された時点で保持される変数にデータを手動でコピーする必要があります。

## <a name="requirements"></a>必要条件

**ヘッダー ファイル:** \<msclr\marshal.h >、 \<msclr\marshal_windows.h >、 \<msclr\marshal_cppstd.h >、または\<msclr\marshal_atl.h >

**Namespace:** msclr::interop

## <a name="see-also"></a>関連項目

[C++ におけるマーシャリングの概要](../dotnet/overview-of-marshaling-in-cpp.md)<br/>
[marshal_as](../dotnet/marshal-as.md)<br/>
[marshal_context クラス](../dotnet/marshal-context-class.md)