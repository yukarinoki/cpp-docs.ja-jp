---
title: 最後に |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- finally keyword [C++]
ms.assetid: b55f3c8e-1af0-43e8-bcfb-99c3685d2578
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 818ee6736d51303b047cb5a47aae02441557db29
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46447285"
---
# <a name="finally"></a>finally

ほかに`try`と`catch`句、CLR の例外処理のサポート、`finally`句。 セマンティクスは次のと同じ、`__finally`で構造化例外処理 (SEH) をブロックします。 A`__finally`次のブロックを`try`または`catch`ブロックします。

## <a name="remarks"></a>Remarks

目的、`finally`ブロックは、例外が発生した後に残されているリソースをクリーンアップします。 なお、`finally`例外がスローされなかった場合でも、ブロックは実行常にされます。 `catch`マネージ例外がスローされた場合にのみ、ブロックが実行に関連付けられている`try`ブロックします。

`finally` 状況依存のキーワードは、します。参照してください[状況依存のキーワード](../windows/context-sensitive-keywords-cpp-component-extensions.md)詳細についてはします。

## <a name="example"></a>例

次の例では、単純な`finally`ブロック。

```
// keyword__finally.cpp
// compile with: /clr
using namespace System;

ref class MyException: public System::Exception{};

void ThrowMyException() {
   throw gcnew MyException;
}

int main() {
   try {
      ThrowMyException();
   }
   catch ( MyException^ e ) {
      Console::WriteLine(  "in catch" );
      Console::WriteLine( e->GetType() );
   }
   finally {
      Console::WriteLine(  "in finally" );
   }
}
```

```Output
in catch
MyException
in finally
```

## <a name="see-also"></a>関連項目

[例外処理](../windows/exception-handling-cpp-component-extensions.md)