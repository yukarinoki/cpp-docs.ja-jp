---
title: '方法: System::String の文字にアクセスする'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- characters [C++], accessing in System::String
- examples [C++], strings
- strings [C++], accessing characters
ms.assetid: cfc89756-aef3-4988-907e-fb236dcb7087
ms.openlocfilehash: 3c44c5e7651bb1c5b4c28654b896cbe64bd5bec7
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2019
ms.locfileid: "79545343"
---
# <a name="how-to-access-characters-in-a-systemstring"></a>方法: System::String の文字にアクセスする

<xref:System.String> オブジェクトの文字にアクセスして、`wchar_t*` 文字列を受け取るアンマネージ関数に対する高パフォーマンスの呼び出しを行うことができます。 メソッドは、<xref:System.String> オブジェクトの最初の文字への内部ポインターを生成します。 このポインターは、直接操作したり固定したりすることができ、通常の `wchar_t` 文字列を必要とする関数に渡すことができます。

## <a name="example"></a>例

`PtrToStringChars` は、内部ポインター (`byref`とも呼ばれます) である <xref:System.Char>を返します。 そのため、ガベージコレクションの対象になります。 ネイティブ関数に渡す場合を除き、このポインターを固定する必要はありません。

次のコードについて考えてみましょう。  `ppchar` が内部ポインターであるため、固定は必要ありません。ガベージコレクターが指す文字列を移動すると、`ppchar`も更新されます。 [Pin_ptr (C++/cli)](../extensions/pin-ptr-cpp-cli.md)を使用しない場合、コードは機能しますが、ピン留めによってパフォーマンスが低下する可能性はありません。

`ppchar` をネイティブ関数に渡す場合は、固定ポインターである必要があります。ガベージコレクターは、アンマネージスタックフレーム上のポインターを更新できません。

```cpp
// PtrToStringChars.cpp
// compile with: /clr
#include<vcclr.h>
using namespace System;

int main() {
   String ^ mystring = "abcdefg";

   interior_ptr<const Char> ppchar = PtrToStringChars( mystring );

   for ( ; *ppchar != L'\0'; ++ppchar )
      Console::Write(*ppchar);
}
```

```Output
abcdefg
```

## <a name="example"></a>例

この例では、ピン留めが必要な場所を示します。

```cpp
// PtrToStringChars_2.cpp
// compile with: /clr
#include <string.h>
#include <vcclr.h>
// using namespace System;

size_t getlen(System::String ^ s) {
   // Since this is an outside string, we want to be secure.
   // To be secure, we need a maximum size.
   size_t maxsize = 256;
   // make sure it doesn't move during the unmanaged call
   pin_ptr<const wchar_t> pinchars = PtrToStringChars(s);
   return wcsnlen(pinchars, maxsize);
};

int main() {
   System::Console::WriteLine(getlen("testing"));
}
```

```Output
7
```

## <a name="example"></a>例

内部ポインターには、ネイティブC++ポインターのすべてのプロパティが含まれています。 たとえば、このメソッドを使用して、リンクされたデータ構造を調べ、1つのポインターだけを使用して挿入と削除を行うことができます。

```cpp
// PtrToStringChars_3.cpp
// compile with: /clr /LD
using namespace System;
ref struct ListNode {
   Int32 elem;
   ListNode ^ Next;
};

void deleteNode( ListNode ^ list, Int32 e ) {
   interior_ptr<ListNode ^> ptrToNext = &list;
   while (*ptrToNext != nullptr) {
      if ( (*ptrToNext) -> elem == e )
         *ptrToNext = (*ptrToNext) -> Next;   // delete node
      else
         ptrToNext = &(*ptrToNext) -> Next;   // move to next node
   }
}
```

## <a name="see-also"></a>参照

[C++ Interop (暗黙の PInvoke) の使用](../dotnet/using-cpp-interop-implicit-pinvoke.md)
