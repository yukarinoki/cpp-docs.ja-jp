---
title: marshal_context::marshal_as
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- marshal_context::marshal_as
- marshal_context.marshal_as
- msclr.interop.marshal_context.marshal_as
- msclr::interop::marshal_context::marshal_as
helpviewer_keywords:
- marshal_context class [C++], operations
ms.assetid: 24a1afee-51c0-497c-948c-f77fe43635c8
ms.openlocfilehash: b097fda0870b2f49d4883e0fafd48f9637d28853
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50649776"
---
# <a name="marshalcontextmarshalas"></a>marshal_context::marshal_as

マネージとネイティブ データ型の間で変換する特定のデータ オブジェクトにマーシャ リングを実行します。

## <a name="syntax"></a>構文

```
To_Type marshal_as<To_Type>(
   From_Type input
);
```

#### <a name="parameters"></a>パラメーター

*input*<br/>
[in]値にマーシャ リングする、`To_Type`変数。

## <a name="return-value"></a>戻り値

`To_Type`の値を変換した後の `input` 型の変数。

## <a name="remarks"></a>Remarks

この関数は、特定のデータ オブジェクトにマーシャ リングを実行します。 この関数のテーブルで示された変換でのみ使用[c++ Overview of Marshaling](../dotnet/overview-of-marshaling-in-cpp.md)します。

サポートされていないデータ型のペアをマーシャ リングしようとする場合`marshal_as`エラーが生成されます[C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md)コンパイル時にします。 詳細については、このエラーと共に提供されるメッセージを参照してください。 `C4996` エラーは、非推奨の関数の場合に加えて、他の状況で生成される可能性もあります。 このエラーを生成する 2 つの条件はサポートされていないデータ型のペアをマーシャ リングしようとしてを使用しようとしています。`marshal_as`のコンテキストを必要とする変換。

マーシャリング ライブラリは、複数のヘッダー ファイルで構成されます。 どの変換でもただ 1 つのファイルが必要ですが、他の変換で必要とされる追加ファイルをインクルードすることもできます。 テーブルに`Marshaling Overview in C++`変換ごとに含まれるマーシャ リングするファイルを示します。

## <a name="example"></a>例

この例からのマーシャ リングするためのコンテキストで作成、`System::String`を`const char *`変数の型。 変換後のデータは、コンテキストを削除する行の後に有効なされません。

```
// marshal_context_test.cpp
// compile with: /clr
#include <stdlib.h>
#include <string.h>
#include <msclr\marshal.h>

using namespace System;
using namespace msclr::interop;

int main() {
   marshal_context^ context = gcnew marshal_context();
   String^ message = gcnew String("Test String to Marshal");
   const char* result;
   result = context->marshal_as<const char*>( message );
   delete context;
   return 0;
}
```

## <a name="requirements"></a>必要条件

**ヘッダー ファイル:** \<msclr\marshal.h >、 \<msclr\marshal_windows.h >、 \<msclr\marshal_cppstd.h >、または\<msclr\marshal_atl.h >

**Namespace:** msclr::interop

## <a name="see-also"></a>関連項目

[C++ におけるマーシャリングの概要](../dotnet/overview-of-marshaling-in-cpp.md)<br/>
[marshal_as](../dotnet/marshal-as.md)<br/>
[marshal_context クラス](../dotnet/marshal-context-class.md)