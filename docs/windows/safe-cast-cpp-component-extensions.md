---
title: safe_cast (C++ コンポーネント拡張) |Microsoft Docs
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
ms.openlocfilehash: 57f59aa201a60fb2cf118b31eb4be377cd246ece
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2018
ms.locfileid: "39606385"
---
# <a name="safecast-c-component-extensions"></a>safe_cast (C++ コンポーネント拡張)
**Safe_cast**操作成功した場合、指定された型として指定された式を返します。 それ以外の場合、がスローされます`InvalidCastException`します。  
  
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
  
## <a name="windows-runtime"></a>Windows ランタイム  
 **safe_cast**指定された式の型を変更することができます。 使用することができますが完全に予想される変数またはパラメーターを特定の型に変換できる場合、 **safe_cast**せず、 **try catch**開発時にプログラミング エラーを検出するためにブロック。 詳細については、次を参照してください。[キャスト (C + + CX)](http://msdn.microsoft.com/library/windows/apps/hh755802.aspx)します。  
  
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
  
### <a name="remarks"></a>Remarks  
 **safe_cast**スロー`InvalidCastException`変換できない場合*式*で指定された型に*タイプ id*します。キャッチする`InvalidCastException`、指定、 [/EH (例外処理モデル)](../build/reference/eh-exception-handling-model.md)コンパイラ オプション、および使用して、 **try ~ catch**ステートメント。  
  
### <a name="requirements"></a>要件  
 コンパイラ オプション: `/ZW`  
  
### <a name="examples"></a>使用例  
  
 次のコード例は、使用する方法を示します**safe_cast** Windows ランタイムとします。  
  
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
  
 **出力**  
  
```Output  
Caught expected exception: InvalidCastException  
```  
  
## <a name="common-language-runtime"></a>共通言語ランタイム 
 **safe_cast**式の型を変更し、検証可能な MSIL コードを生成することができます。  
  
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
  
### <a name="remarks"></a>Remarks  
 式`safe_cast<`*タイプ id*`>(`*式*`)`オペランド式 type-id 型のオブジェクトに変換します。  
  
 コンパイラでは使用、 [static_cast](../cpp/static-cast-operator.md)受け付けることがほとんどの場所で、 **safe_cast**します。  ただし、 **safe_cast** 、検証可能な MSIL を生成することが保証されますが、 **static_cast**検証できない MSIL を生成する可能性があります。  参照してください[純粋で検証可能なコード (C +/cli CLI)](../dotnet/pure-and-verifiable-code-cpp-cli.md)と[Peverify.exe (PEVerify ツール)](/dotnet/framework/tools/peverify-exe-peverify-tool)検証可能なコードの詳細についてはします。  
  
 ような**static_cast**、 **safe_cast**ユーザー定義の変換を呼び出します。  
  
 キャストの詳細については、次を参照してください。[キャスト演算子](../cpp/casting-operators.md)します。  
  
 **safe_cast**は適用されませんを**const_cast** (キャスト**const**)。  
  
 **safe_cast** cli 名前空間にあります。  参照してください[プラットフォーム、既定では、および cli 名前空間](../windows/platform-default-and-cli-namespaces-cpp-component-extensions.md)詳細についてはします。  
  
 詳細については**safe_cast**を参照してください。  
  
-   [C スタイル キャストと/clr (C +/cli CLI)](../windows/c-style-casts-with-clr-cpp-cli.md)  
  
-   [方法: C++/CLI で safe_cast を使用する](../dotnet/how-to-use-safe-cast-in-cpp-cli.md)  

### <a name="requirements"></a>要件  
 コンパイラ オプション: `/clr`  
  
### <a name="examples"></a>使用例  
  
 1 つ、コンパイラが受け入れませんの例を**static_cast**は受け入れ、 **safe_cast**関連していないインターフェイス型間のキャストです。  **Safe_cast**コンパイラは、変換エラーを発行しませんし、キャストが可能かどうかを実行時のチェックが実行  
  
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