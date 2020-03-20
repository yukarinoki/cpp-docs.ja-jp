---
title: finally
ms.date: 11/04/2016
helpviewer_keywords:
- finally keyword [C++]
ms.assetid: b55f3c8e-1af0-43e8-bcfb-99c3685d2578
ms.openlocfilehash: 2574ba5a10bbf5eddc68d6e0265d5dfc99c6d8fc
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2019
ms.locfileid: "79545097"
---
# <a name="finally"></a>finally

CLR 例外処理では、`try` と `catch` の句に加え、`finally` 句もサポートしています。 セマンティクスは、構造化例外処理 (SEH) の `__finally` ブロックと同じです。 `__finally` ブロックは、`try` または `catch` ブロックの後に続くことができます。

## <a name="remarks"></a>コメント

`finally` ブロックの目的は、例外が発生した後に残されたすべてのリソースをクリーンアップすることです。 例外がスローされなかった場合でも、`finally` ブロックは常に実行されることに注意してください。 `catch` ブロックは、関連付けられた `try` ブロック内でマネージ例外がスローされた場合にのみ実行されます。

`finally` は、状況依存のキーワードです。詳細については[、「状況依存のキーワード](../extensions/context-sensitive-keywords-cpp-component-extensions.md)」を参照してください。

## <a name="example"></a>例

単純な `finally` ブロックの例を次に示します。

```cpp
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

## <a name="see-also"></a>参照

[例外処理](../extensions/exception-handling-cpp-component-extensions.md)
