---
title: marshal_context クラス
ms.date: 01/16/2019
ms.topic: reference
f1_keywords:
- msclr::interop::marshal_context::marshal_context
- msclr::interop::marshal_context::marshal_as
helpviewer_keywords:
- msclr::marshal_context class [C++]
ms.assetid: 241b0cf6-4ca4-4812-aaee-d671c11dc034
ms.openlocfilehash: aa5935332cfa12c02e8084136a311a7593a4f3b9
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/29/2020
ms.locfileid: "91508580"
---
# <a name="marshal_context-class"></a>marshal_context クラス

このクラスは、ネイティブ環境とマネージ環境の間でデータを変換します。

## <a name="syntax"></a>構文

```cpp
class marshal_context
```

## <a name="remarks"></a>解説

`marshal_context`コンテキストを必要とするデータ変換には、クラスを使用します。 コンテキストを必要とする変換と、どのマーシャリングファイルを含める必要があるかの詳細については、「 [C++ におけるマーシャリングの概要](../dotnet/overview-of-marshaling-in-cpp.md)」を参照してください。 コンテキストを使用する場合のマーシャリングの結果は、 `marshal_context` オブジェクトが破棄されるまで有効です。 結果を保持するには、データをコピーする必要があります。

同じを `marshal_context` 使用して、さまざまなデータ変換を行うことができます。 この方法でコンテキストを再利用しても、以前のマーシャリング呼び出しの結果には影響しません。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|---------|-----------|
|[marshal_context::marshal_context](#marshal-context)|`marshal_context`マネージデータ型とネイティブデータ型の間のデータ変換に使用するオブジェクトを構築します。|
|[marshal_context:: ~ marshal_context](#tilde-marshal-context)|`marshal_context` オブジェクトを破棄します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|---------|-----------|
|[marshal_context::marshal_as](#marshal-as)|特定のデータオブジェクトに対してマーシャリングを実行し、マネージデータ型とネイティブデータ型との間で変換を実行します。|

## <a name="requirements"></a>必要条件

**ヘッダーファイル:** \<msclr\marshal.h> 、 \<msclr\marshal_windows.h> 、 \<msclr\marshal_cppstd.h> 、または \<msclr\marshal_atl.h>

**名前空間:** msclr:: interop

## <a name="marshal_contextmarshal_context"></a><a name="marshal-context"></a> marshal_context:: marshal_context

`marshal_context`マネージデータ型とネイティブデータ型の間のデータ変換に使用するオブジェクトを構築します。

```cpp
marshal_context();
```

### <a name="remarks"></a>注釈

一部のデータ変換にはマーシャリングコンテキストが必要です。 コンテキストを必要とする翻訳と、アプリケーションに含める必要のあるマーシャリングファイルの詳細については、「 [C++ におけるマーシャリングの概要](../dotnet/overview-of-marshaling-in-cpp.md)」を参照してください。

### <a name="example"></a>例

[Marshal_context:: marshal_as](#marshal-as)の例を参照してください。

## <a name="marshal_contextmarshal_context"></a><a name="tilde-marshal-context"></a> marshal_context:: ~ marshal_context

`marshal_context` オブジェクトを破棄します。

```cpp
~marshal_context();
```

### <a name="remarks"></a>注釈

一部のデータ変換にはマーシャリングコンテキストが必要です。 どの変換にコンテキストが必要であり、どのマーシャリングファイルをアプリケーションに含める必要があるかの詳細については、「 [C++ でのマーシャリングの概要](../dotnet/overview-of-marshaling-in-cpp.md) 」を参照してください。

オブジェクトを削除すると `marshal_context` 、そのコンテキストによって変換されたデータが無効になります。 オブジェクトが破棄された後にデータを保持する場合は、 `marshal_context` 永続化される変数にデータを手動でコピーする必要があります。

## <a name="marshal_contextmarshal_as"></a><a name="marshal-as"></a> marshal_context:: marshal_as

特定のデータオブジェクトに対してマーシャリングを実行し、マネージデータ型とネイティブデータ型との間で変換を実行します。

```cpp
To_Type marshal_as<To_Type>(
   From_Type input
);
```

### <a name="parameters"></a>パラメーター

*input*<br/>
から変数にマーシャリングする値です `To_Type` 。

### <a name="return-value"></a>戻り値

`To_Type`の変換後の値である型の変数 `input` 。

### <a name="remarks"></a>注釈

この関数は、特定のデータオブジェクトに対してマーシャリングを実行します。 この関数は、 [「C++ におけるマーシャリングの概要](../dotnet/overview-of-marshaling-in-cpp.md)」の表に示されている変換でのみ使用してください。

サポートされていないデータ型のペアをマーシャリングしようとすると、 `marshal_as` コンパイル時にによってエラー [C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md) が生成されます。 詳細については、このエラーと共に提供されるメッセージを参照してください。 `C4996` エラーは、非推奨の関数の場合に加えて、他の状況で生成される可能性もあります。 このエラーを生成する2つの条件では、サポートされていないデータ型のペアをマーシャリングしようとして、コンテキストを必要とする変換に使用しようとしてい `marshal_as` ます。

マーシャリング ライブラリは、複数のヘッダー ファイルで構成されます。 どの変換でもただ 1 つのファイルが必要ですが、他の変換で必要とされる追加ファイルをインクルードすることもできます。 の表は、 `Marshaling Overview in C++` 各変換に含めるマーシャリングファイルを示しています。

### <a name="example"></a>例

この例では、から変数型にマーシャリングするためのコンテキストを作成し `System::String` `const char *` ます。 変換されたデータは、コンテキストを削除する行の後で有効になりません。

```cpp
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
