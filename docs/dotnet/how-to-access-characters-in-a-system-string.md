---
title: '方法: System::String の文字にアクセスする'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- characters [C++], accessing in System::String
- examples [C++], strings
- strings [C++], accessing characters
ms.assetid: cfc89756-aef3-4988-907e-fb236dcb7087
ms.openlocfilehash: a91f82d0377b9065c2927e61e9f2a558a49985f0
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87221368"
---
# <a name="how-to-access-characters-in-a-systemstring"></a>方法: System::String の文字にアクセスする

オブジェクトの文字にアクセスして、 <xref:System.String> 文字列を受け取るアンマネージ関数に対する高パフォーマンスの呼び出しを行うことができ `wchar_t*` ます。 メソッドは、オブジェクトの最初の文字への内部ポインターを生成し <xref:System.String> ます。 このポインターを直接操作したり、固定して、通常の文字列を必要とする関数に渡すことができ **`wchar_t`** ます。

## <a name="example"></a>例

`PtrToStringChars`<xref:System.Char>内部ポインター (とも呼ばれます) であるを返し `byref` ます。 そのため、ガベージコレクションの対象になります。 ネイティブ関数に渡す場合を除き、このポインターを固定する必要はありません。

次のコードについて考えてみましょう。  は内部ポインターであるため、固定は必要ありません。また、 `ppchar` ガベージコレクターが指す文字列を移動すると、も更新され `ppchar` ます。 [Pin_ptr (C++/cli)](../extensions/pin-ptr-cpp-cli.md)を使用しない場合、コードは機能しますが、ピン留めによってパフォーマンスが低下する可能性はありません。

をネイティブ関数に渡す場合は、 `ppchar` 固定ポインターである必要があります。ガベージコレクターは、アンマネージスタックフレーム上のポインターを更新できません。

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

内部ポインターには、ネイティブ C++ ポインターのすべてのプロパティが含まれています。 たとえば、このメソッドを使用して、リンクされたデータ構造を調べ、1つのポインターだけを使用して挿入と削除を行うことができます。

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

## <a name="see-also"></a>関連項目

[C++ Interop (暗黙の PInvoke) の使用](../dotnet/using-cpp-interop-implicit-pinvoke.md)
