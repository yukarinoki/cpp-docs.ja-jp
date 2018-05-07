---
title: '方法: system::string の文字にアクセス |Microsoft ドキュメント'
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- characters [C++], accessing in System::String
- examples [C++], strings
- strings [C++], accessing characters
ms.assetid: cfc89756-aef3-4988-907e-fb236dcb7087
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: ed9682492eedc915919758d42d5594560cb4a83a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-access-characters-in-a-systemstring"></a>方法: System::String の文字にアクセスする
文字にアクセスすることができます、<xref:System.String>アンマネージ呼び出しを高パフォーマンスのためのオブジェクトの関数を受け取る`wchar_t*`文字列。 メソッドの最初の文字への内部ポインターを生成する、<xref:System.String>オブジェクト。 このポインター直接操作またはピン留めして通常必要とする関数に渡される`wchar_t`文字列。  
  
## <a name="example"></a>例  
 `PtrToStringChars` 返します、 <xref:System.Char>、内部ポインターである (とも呼ばれる、 `byref`)。 そのため、ガベージ コレクションの対象となります。 ネイティブ関数に渡すしようとしている場合を除き、このポインターをピン留めする必要はありません。  
  
 次のコードについて考えてみましょう。  ピン留めは必要ありませんので`ppchar`内部ポインターであり、ガベージ コレクターが指す文字列を移動した場合は更新も`ppchar`します。 なし、 [pin_ptr (C + + CLI)](../windows/pin-ptr-cpp-cli.md)されませんが、パフォーマンスが低下の原因となったをピン留めする、コードが動作します。  
  
 渡す場合`ppchar`ネイティブ関数にする必要があります固定ポインター以外の場合は、ガベージ コレクターは、アンマネージのスタック フレーム上のポインターを更新できません。  
  
```  
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
 この例は、ピン留めが必要な場所を示します。  
  
```  
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
 内部ポインターには、ネイティブ C++ ポインターのすべてのプロパティがあります。 たとえば、リンクされているデータ構造を紹介し、挿入と 1 つだけのポインターを使用して削除を使用することができます。  
  
```  
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