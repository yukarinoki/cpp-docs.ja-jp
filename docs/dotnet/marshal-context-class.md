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
ms.openlocfilehash: 110fe4abf7eb90b05e7feef563efa4882bed0fc6
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81332009"
---
# <a name="marshal_context-class"></a>marshal_context クラス

このクラスは、ネイティブ環境とマネージ環境の間でデータを変換します。

## <a name="syntax"></a>構文

```cpp
class marshal_context
```

## <a name="remarks"></a>解説

コンテキストを`marshal_context`必要とするデータ変換のクラスを使用します。 コンテキストを必要とする変換と、どのマーシャリング ファイルを含める必要があるかについては、「 [C++ でのマーシャリングの概要](../dotnet/overview-of-marshaling-in-cpp.md)」を参照してください。 コンテキストを使用した場合のマーシャリングの結果は、オブジェクトが破棄されるまで`marshal_context`有効です。 結果を保存するには、データをコピーする必要があります。

同じ`marshal_context`数のデータ変換にも使用できます。 この方法でコンテキストを再利用しても、以前のマーシャリング呼び出しの結果には影響しません。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|---------|-----------|
|[marshal_context::marshal_context](#marshal-context)|マネージ データ`marshal_context`型とネイティブ データ型の間のデータ変換に使用するオブジェクトを構築します。|
|[marshal_context::~marshal_context](#tilde-marshal-context)|`marshal_context` オブジェクトを破棄します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|---------|-----------|
|[marshal_context::marshal_as](#marshal-as)|特定のデータ オブジェクトにマーシャリングを実行して、マネージ データ型とネイティブ データ型の間でマーシャリングを行います。|

## <a name="requirements"></a>必要条件

**ヘッダー ファイル:** \<msclr\marshal.h \<>、msclr\marshal_windows.h>、msclr\marshal_cppstd.h \<>、または\<msclr\marshal_atl.h>

**名前空間:** msclr::相互運用機能

## <a name="marshal_contextmarshal_context"></a><a name="marshal-context"></a>marshal_context::marshal_context

マネージ データ`marshal_context`型とネイティブ データ型の間のデータ変換に使用するオブジェクトを構築します。

```cpp
marshal_context();
```

### <a name="remarks"></a>解説

データ変換によっては、マーシャリング コンテキストが必要なものもあります。 コンテキストを必要とする変換と、アプリケーションに含める必要があるマーシャリング ファイルの詳細については、「 [C++ でのマーシャリングの概要](../dotnet/overview-of-marshaling-in-cpp.md)」を参照してください。

### <a name="example"></a>例

[marshal_context::marshal_as](../dotnet/marshal-context-marshal-as.md)の例を参照してください。

## <a name="marshal_contextmarshal_context"></a><a name="tilde-marshal-context"></a>marshal_context::~marshal_context

`marshal_context` オブジェクトを破棄します。

```cpp
~marshal_context();
```

### <a name="remarks"></a>解説

データ変換によっては、マーシャリング コンテキストが必要なものもあります。 どの変換でコンテキストが必要か、どのマーシャリング ファイルをアプリケーションに含める必要があるかについて詳しくは[、「C++](../dotnet/overview-of-marshaling-in-cpp.md)でのマーシャリングの概要」をご覧ください。

オブジェクトを`marshal_context`削除すると、そのコンテキストによって変換されたデータが無効になります。 オブジェクトが破棄された後にデータを`marshal_context`保持する場合は、データを保持する変数に手動でコピーする必要があります。

## <a name="marshal_contextmarshal_as"></a><a name="marshal-as"></a>marshal_context::marshal_as

特定のデータ オブジェクトにマーシャリングを実行して、マネージ データ型とネイティブ データ型の間でマーシャリングを行います。

```cpp
To_Type marshal_as<To_Type>(
   From_Type input
);
```

### <a name="parameters"></a>パラメーター

*input*<br/>
[in]変数にマーシャリングする値。 `To_Type`

### <a name="return-value"></a>戻り値

変換された値である`To_Type`型の`input`変数。

### <a name="remarks"></a>解説

この関数は、特定のデータ オブジェクトに対してマーシャリングを実行します。 この関数は、「 C++ での[マーシャリングの概要](../dotnet/overview-of-marshaling-in-cpp.md)」の表で示されている変換でのみ使用します。

サポートされていないデータ型のペアをマーシャリングしようとすると、`marshal_as`コンパイル時にエラー [C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md)が生成されます。 詳細については、このエラーと共に提供されるメッセージを参照してください。 `C4996` エラーは、非推奨の関数の場合に加えて、他の状況で生成される可能性もあります。 このエラーを生成する 2 つの条件は、サポートされていないデータ型のペアをマーシャリングしようとし、コンテキスト`marshal_as`を必要とする変換に使用しようとしています。

マーシャリング ライブラリは、複数のヘッダー ファイルで構成されます。 どの変換でもただ 1 つのファイルが必要ですが、他の変換で必要とされる追加ファイルをインクルードすることもできます。 の表は`Marshaling Overview in C++`、変換ごとにどのマーシャリング ファイルを含める必要があるかを示しています。

### <a name="example"></a>例

この例では、 から`System::String`変数型へのマーシャリングの`const char *`コンテキストを作成します。 変換されたデータは、コンテキストを削除する行の後には有効ではありません。

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
