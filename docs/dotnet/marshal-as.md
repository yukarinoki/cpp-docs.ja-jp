---
description: '詳細については、次を参照してください: marshal_as'
title: marshal_as
ms.date: 07/12/2019
ms.topic: reference
f1_keywords:
- marshal_as
- msclr.interop.marshal_as
- msclr::interop::marshal_as
helpviewer_keywords:
- marshal_as template [C++]
ms.assetid: 2ed717da-2b11-41e5-981d-47d251771989
ms.openlocfilehash: 0b0738b8778b287e2e97f074345a10841c70a7b1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97253625"
---
# <a name="marshal_as"></a>marshal_as

このメソッドは、ネイティブ環境とマネージド環境の間でデータを変換します。

## <a name="syntax"></a>構文

```
To_Type marshal_as<To_Type>(
   From_Type input
);
```

#### <a name="parameters"></a>パラメーター

*input*<br/>
から変数にマーシャリングする値です `To_Type` 。

## <a name="return-value"></a>戻り値

`To_Type`の値を変換した後の `input` 型の変数。

## <a name="remarks"></a>解説

このメソッドは、ネイティブ型とマネージド型の間でデータを変換する簡素化された方法を提供します。 サポートされているデータ型を確認するには、「 [C++ におけるマーシャリングの概要](../dotnet/overview-of-marshaling-in-cpp.md)」を参照してください。 一部のデータ変換では、コンテキストが必要です。 [Marshal_context クラス](../dotnet/marshal-context-class.md)を使用して、これらのデータ型を変換できます。

サポートされていないデータ型のペアをマーシャリングしようとすると、 `marshal_as` コンパイル時にによってエラー [C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md) が生成されます。 詳細については、このエラーと共に提供されるメッセージを参照してください。 `C4996` エラーは、非推奨の関数の場合に加えて、他の状況で生成される可能性もあります。 このエラーの 1 つの例は、サポートされていない 2 つのデータ型をマーシャリングしようとする場合です。

マーシャリング ライブラリは、複数のヘッダー ファイルで構成されます。 どの変換でもただ 1 つのファイルが必要ですが、他の変換で必要とされる追加ファイルをインクルードすることもできます。 どのファイルにどの変換が関連付けられているかを確認するには、`Marshaling Overview` の表を参照してください。 どの変換を行おうとするかにかかわりなく、名前空間の要件が常に有効になります。

`System::ArgumentNullException(_EXCEPTION_NULLPTR)`入力パラメーターが null の場合にスローします。

## <a name="example"></a>例

この例では、`const char*` から `System::String` 変数型へのマーシャリングを行います。

```cpp
// marshal_as_test.cpp
// compile with: /clr
#include <stdlib.h>
#include <string.h>
#include <msclr\marshal.h>

using namespace System;
using namespace msclr::interop;

int main() {
   const char* message = "Test String to Marshal";
   String^ result;
   result = marshal_as<String^>( message );
   return 0;
}
```

## <a name="requirements"></a>要件

**ヘッダーファイル:** \<msclr\marshal.h> 、 \<msclr\marshal_windows.h> 、 \<msclr\marshal_cppstd.h> 、または \<msclr\marshal_atl.h>

**名前空間:** msclr:: interop

## <a name="see-also"></a>関連項目

[C++ におけるマーシャリングの概要](../dotnet/overview-of-marshaling-in-cpp.md)<br/>
[marshal_context クラス](../dotnet/marshal-context-class.md)
