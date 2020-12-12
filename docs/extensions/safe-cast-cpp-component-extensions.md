---
description: '詳細情報: safe_cast (C++/CLI および C++/CX)'
title: safe_cast (C++/CLI および C++/CX)
ms.date: 10/12/2018
ms.topic: reference
f1_keywords:
- safe_cast
- safe_cast_cpp
- stdcli::language::safe_cast
helpviewer_keywords:
- safe_cast keyword [C++]
ms.assetid: 4fa688bf-a8ec-49bc-a4c5-f48134efa4f7
ms.openlocfilehash: 7753af357fd782a513ce941b42ad0433ca24b0dd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97172948"
---
# <a name="safe_cast-ccli-and-ccx"></a>safe_cast (C++/CLI および C++/CX)

**safe_cast** 操作は、指定された式を指定した型で返します (成功した場合)。失敗した場合は、`InvalidCastException` をスローします。

## <a name="all-runtimes"></a>すべてのランタイム

(この言語機能にはランタイムに適用される特記事項がありません。)

### <a name="syntax"></a>構文

```cpp
[default]:: safe_cast< type-id >( expression )
```

## <a name="windows-runtime"></a>Windows ランタイム

**safe_cast** を使用して、指定された式の型を変更できます。 変数またはパラメーターを特定の型に問題なく変換できることがわかっている場合、**try-catch** ブロックを使用せずに **safe_cast** を使用して、開発中のプログラミング エラーを検出することができます。 詳細については、「[キャスト (C++/CX)](../cppcx/casting-c-cx.md)」を参照してください。

### <a name="syntax"></a>構文

```cpp
[default]:: safe_cast< type-id >( expression )
```

### <a name="parameters"></a>パラメーター

*種類-id*<br/>
変換後の *expression* の型。 参照型または値型へのハンドル、値型、参照型または値型への追跡参照。

*式 (expression)*<br/>
参照型または値型へのハンドル、値型、参照型または値型への追跡参照として評価される式。

### <a name="remarks"></a>解説

**safe_cast** は、 `InvalidCastException` *式* を *型 id* で指定された型に変換できない場合は、をスローします。キャッチするには、/ `InvalidCastException` [EH (例外処理モデル)](../build/reference/eh-exception-handling-model.md) コンパイラオプションを指定し、 **try/catch** ステートメントを使用します。

### <a name="requirements"></a>要件

コンパイラ オプション: `/ZW`

### <a name="examples"></a>例

次のコード例では、Windows ランタイムで **safe_cast** を使用する方法を示します。

```cpp
// safe_cast_ZW.cpp
// compile with: /ZW /EHsc

using namespace default;
using namespace Platform;

interface class I1 {};
interface class I2 {};
interface class I3 {};

ref class X : public I1, public I2 {};

int main(Array<String^>^ args) {
   I1^ i1 = ref new X;
   I2^ i2 = safe_cast<I2^>(i1);   // OK, I1 and I2 have common type: X
   // I2^ i3 = static_cast<I2^>(i1);   C2440 use safe_cast instead
   try {
      I3^ i4 = safe_cast<I3^>(i1);   // Fails because i1 is not derived from I3.
   }
   catch(InvalidCastException^ ic) {
   wprintf(L"Caught expected exception: %s\n", ic->Message);
   }
}
```

```Output
Caught expected exception: InvalidCastException
```

## <a name="common-language-runtime"></a>共通言語ランタイム

**safe_cast** を使用して、式の型を変更し、検証可能な MSIL コードを生成できます。

### <a name="syntax"></a>構文

```cpp
[cli]:: safe_cast< type-id >( expression )
```

### <a name="parameters"></a>パラメーター

*種類-id*<br/>
参照型または値型へのハンドル、値型、参照型または値型への追跡参照。

*式 (expression)*<br/>
参照型または値型へのハンドル、値型、参照型または値型への追跡参照として評価される式。

### <a name="remarks"></a>解説

式の `safe_cast<` *型 id* `>(` *式* は、 `)` オペランド *式* を型 *id* 型のオブジェクトに変換します。

コンパイラでは、[safe_cast](../cpp/static-cast-operator.md) を使用できるほとんどの場所で、**safe_cast** を使用できます。  ただし、 **safe_cast** は検証可能な msil を生成することが保証されますが、では **`static_cast`** 検証できない msil が生成される可能性があります。  検証可能なコードの詳細については、「[純粋なコードと検証可能なコード (C++/CLI)](../dotnet/pure-and-verifiable-code-cpp-cli.md)」と「[Peverify.exe (PEVerify ツール)](/dotnet/framework/tools/peverify-exe-peverify-tool)」を参照してください。

と同様 **`static_cast`** に、 **safe_cast** はユーザー定義の変換を呼び出します。

キャストの詳細については、「[キャスト演算子](../cpp/casting-operators.md)」を参照してください。

**safe_cast** は、 **`const_cast`** (cast) を適用 **`const`** しません。

**safe_cast** は cli 名前空間に存在します。  詳細については、「[プラットフォーム、既定、および cli 名前空間](platform-default-and-cli-namespaces-cpp-component-extensions.md)」を参照してください。

**safe_cast** の詳細については、以下を参照してください。

- [C スタイル キャストと /clr (C++/CLI)](c-style-casts-with-clr-cpp-cli.md)

- [方法: C++/CLI で safe_cast を使用する](../dotnet/how-to-use-safe-cast-in-cpp-cli.md)

### <a name="requirements"></a>要件

コンパイラ オプション: `/clr`

### <a name="examples"></a>例

コンパイラがを受け入れないが、safe_cast を受け入れる例の1つとして、関連のない **`static_cast`** インターフェイス型間のキャストがあります。  **safe_cast** を使用した場合、コンパイラは変換エラーを生成せず、キャストが可能であるかどうかを実行時に検証します。

```cpp
// safe_cast.cpp
// compile with: /clr
using namespace System;

interface class I1 {};
interface class I2 {};
interface class I3 {};

ref class X : public I1, public I2 {};

int main() {
   I1^ i1 = gcnew X;
   I2^ i2 = safe_cast<I2^>(i1);   // OK, I1 and I2 have common type: X
   // I2^ i3 = static_cast<I2^>(i1);   C2440 use safe_cast instead
   try {
      I3^ i4 = safe_cast<I3^>(i1);   // fail at runtime, no common type
   }
   catch(InvalidCastException^) {
      Console::WriteLine("Caught expected exception");
   }
}
```

```Output
Caught expected exception
```

## <a name="see-also"></a>関連項目

[.NET および UWP 用のコンポーネントの拡張機能](component-extensions-for-runtime-platforms.md)
