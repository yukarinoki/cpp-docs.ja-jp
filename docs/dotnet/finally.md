---
description: '詳細情報: finally'
title: finally
ms.date: 11/04/2016
helpviewer_keywords:
- finally keyword [C++]
ms.assetid: b55f3c8e-1af0-43e8-bcfb-99c3685d2578
ms.openlocfilehash: 039c3fab7854d045c9b4917d2a0bc9f01fdc61a3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97252156"
---
# <a name="finally"></a>finally

**`try`** および句に加えて **`catch`** 、CLR 例外処理では句がサポートされてい **`finally`** ます。 セマンティクスは、 **`__finally`** 構造化例外処理 (SEH) のブロックと同じです。 **`__finally`** ブロックは、またはブロックの後に使用でき **`try`** **`catch`** ます。

## <a name="remarks"></a>解説

ブロックの目的は、 **`finally`** 例外が発生した後に残されたすべてのリソースをクリーンアップすることです。 **`finally`** 例外がスローされなかった場合でも、ブロックは常に実行されることに注意してください。 **`catch`** ブロックは、関連付けられているブロック内でマネージ例外がスローされた場合にのみ実行され **`try`** ます。

`finally` は、状況依存のキーワードです。詳細については [、「状況依存のキーワード](../extensions/context-sensitive-keywords-cpp-component-extensions.md) 」を参照してください。

## <a name="example"></a>例

単純なブロックの例を次に示し **`finally`** ます。

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

## <a name="see-also"></a>関連項目

[例外処理](../extensions/exception-handling-cpp-component-extensions.md)
