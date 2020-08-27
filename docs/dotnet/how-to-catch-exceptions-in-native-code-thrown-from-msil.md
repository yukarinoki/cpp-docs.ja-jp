---
title: '方法: MSIL からスローされるネイティブ コードの例外をキャッチする'
description: MSIL からスローされたネイティブコードで例外をキャッチする方法の例。
ms.date: 11/04/2016
helpviewer_keywords:
- exceptions, catching
- catching exceptions, thrown from MSIL
- MSIL, catching exceptions in native code
ms.assetid: c15afd2b-8505-43bf-8a4a-f1d41532a124
ms.openlocfilehash: b68a771d27e091f86331703b55bc2eb52dfbb41b
ms.sourcegitcommit: efc8c32205c9d610f40597556273a64306dec15d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2020
ms.locfileid: "88898578"
---
# <a name="how-to-catch-exceptions-in-native-code-thrown-from-msil"></a>方法: MSIL からスローされるネイティブ コードの例外をキャッチする

ネイティブコードでは、MSIL からネイティブ C++ 例外をキャッチできます。  CLR 例外は、およびでキャッチでき **`__try`** **`__except`** ます。

詳細については、「 [構造化例外処理 (C/c + +)](../cpp/structured-exception-handling-c-cpp.md) 」および「 [例外とエラー処理のための最新の C++ のベストプラクティス](../cpp/errors-and-exception-handling-modern-cpp.md)」を参照してください。

## <a name="example-1"></a>例 1

次の例では、2つの関数を持つモジュールを定義しています。1つはネイティブ例外をスローし、もう1つは MSIL 例外をスローします。

```cpp
// catch_MSIL_in_native.cpp
// compile with: /clr /c
void Test() {
   throw ("error");
}

void Test2() {
   throw (gcnew System::Exception("error2"));
}
```

## <a name="example-2"></a>例 2

次の例では、ネイティブ例外と MSIL 例外をキャッチするモジュールを定義しています。

```cpp
// catch_MSIL_in_native_2.cpp
// compile with: /clr catch_MSIL_in_native.obj
#include <iostream>
using namespace std;
void Test();
void Test2();

void Func() {
   // catch any exception from MSIL
   // should not catch Visual C++ exceptions like this
   // runtime may not destroy the object thrown
   __try {
      Test2();
   }
   __except(1) {
      cout << "caught an exception" << endl;
   }

}

int main() {
   // catch native C++ exception from MSIL
   try {
      Test();
   }
   catch(char * S) {
      cout << S << endl;
   }
   Func();
}
```

```Output
error
caught an exception
```

## <a name="see-also"></a>関連項目

[例外処理](../extensions/exception-handling-cpp-component-extensions.md)
