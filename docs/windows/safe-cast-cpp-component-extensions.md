---
title: safe_cast (C++ コンポーネント拡張) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- safe_cast
- safe_cast_cpp
- stdcli::language::safe_cast
dev_langs:
- C++
helpviewer_keywords:
- safe_cast keyword [C++]
ms.assetid: 4fa688bf-a8ec-49bc-a4c5-f48134efa4f7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c889d39df4d900beba5c9b41015e62293fdbbcde
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="safecast-c-component-extensions"></a>safe_cast (C++ コンポーネント拡張)
`safe_cast` 操作は、指定された式を指定した型で返します (成功した場合)。失敗した場合は、`InvalidCastException` をスローします。  
  
## <a name="all-runtimes"></a>すべてのランタイム  
 (この言語機能にはランタイムに適用される特記事項がありません。)  
  
### <a name="syntax"></a>構文  
  
```cpp  
[default]:: safe_cast<  
type-id  
>(  
expression  
)  
  
```  
  
### <a name="parameters"></a>パラメーター  
  
### <a name="remarks"></a>コメント  
  
## <a name="windows-runtime"></a>Windows ランタイム  
 `safe_cast` を使用して、指定された式の型を変更することができます。 変数またはパラメーターを特定の型に問題なく変換できることがわかっている場合、try-catch ブロックを使用せずに safe_cast を使用して、開発中のプログラミング エラーを検出することができます。 詳細については、次を参照してください。[キャスト (C + + CX)](http://msdn.microsoft.com/library/windows/apps/hh755802.aspx)です。  
  
### <a name="syntax"></a>構文  
  
```cpp  
[default]:: safe_cast<  
type-id  
>(  
expression  
)  
  
```  
  
### <a name="parameters"></a>パラメーター  
 *種類 id*  
 変換後の型*式*にします。 参照型または値型へのハンドル、値型、参照型または値型への追跡参照。  
  
 *式*  
 参照型または値型へのハンドル、値型、参照型または値型への追跡参照として評価される式。  
  
### <a name="remarks"></a>コメント  
 `safe_cast` スロー`InvalidCastException`変換できない場合*式*で指定された型に*タイプ id*です。キャッチする`InvalidCastException`を指定して、 [/EH (例外処理モデル)](../build/reference/eh-exception-handling-model.md)コンパイラ オプション、および try ブロックと catch ステートメントを使用します。  
  
### <a name="requirements"></a>要件  
 コンパイラ オプション: **/ZW**  
  
### <a name="examples"></a>使用例  
 **例**  
  
 次のコード例を使用する方法を示しています`safe_cast`Windows ランタイムとします。  
  
```cpp#  
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
  
 **出力**  
  
```Output  
Caught expected exception: InvalidCastException  
```  
  
## <a name="common-language-runtime"></a>共通言語ランタイム 
 `safe_cast` を使用して、式の型を変更し、検証可能な MSIL コードを生成できます。  
  
### <a name="syntax"></a>構文  
  
```cpp  
[cli]:: safe_cast<  
type-id  
>(  
expression  
)  
  
```  
  
### <a name="parameters"></a>パラメーター  
 *種類 id*  
 参照型または値型へのハンドル、値型、参照型または値型への追跡参照。  
  
 *式*  
 参照型または値型へのハンドル、値型、参照型または値型への追跡参照として評価される式。  
  
### <a name="remarks"></a>コメント  
 式`safe_cast<`*タイプ id*`>(`*式*`)` type-id 型のオブジェクトにオペランド式を変換します。  
  
 コンパイラは、受け入れる、 [static_cast](../cpp/static-cast-operator.md)を使用できるほとんどの場所で、`safe_cast`です。  ただし、`safe_cast` では確実に検証可能な MSIL が生成されますが、`static_cast` では検証不可能な MSIL が生成される場合があります。  参照してください[純粋なコードと検証可能なコード (C + + CLI)](../dotnet/pure-and-verifiable-code-cpp-cli.md)と[Peverify.exe (PEVerify ツール)](/dotnet/framework/tools/peverify-exe-peverify-tool)検証可能なコードについての詳細。  
  
 `static_cast` と同様に、`safe_cast` はユーザー定義の変換を呼び出します。  
  
 キャストの詳細については、次を参照してください。[キャスト演算子](../cpp/casting-operators.md)です。  
  
 `safe_cast` 該当なし、 **const_cast** (キャスト**const**)。  
  
 `safe_cast` は cli 名前空間に存在します。  参照してください[プラットフォーム、既定値、および cli 名前空間](../windows/platform-default-and-cli-namespaces-cpp-component-extensions.md)詳細についてはします。  
  
 詳細については**safe_cas**t を参照してください。  
  
-   [C スタイル キャストと/clr (C + + CLI)](../windows/c-style-casts-with-clr-cpp-cli.md)  
  
-   [方法: C++/CLI で safe_cast を使用する](../dotnet/how-to-use-safe-cast-in-cpp-cli.md)  

### <a name="requirements"></a>要件  
 コンパイラ オプション: **/clr**  
  
### <a name="examples"></a>使用例  
 **例**  
  
 コンパイラで `static_cast` を使用できないが `safe_cast` を使用できる状況の例の 1 つは、関連していないインターフェイス型の間でのキャストです。  `safe_cast` を使用した場合、コンパイラは変換エラーを生成せず、キャストが可能であるかどうかを実行時に検証します。  
  
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
  
 **出力**  
  
```Output  
Caught expected exception  
```  
  
## <a name="see-also"></a>関連項目  
 [ランタイム プラットフォームのコンポーネントの拡張機能](../windows/component-extensions-for-runtime-platforms.md)