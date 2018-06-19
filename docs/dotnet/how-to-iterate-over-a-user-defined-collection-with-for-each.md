---
title: '方法: for each を使用のユーザー定義のコレクションを反復 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- collections, iterating over
ms.assetid: 0efd9e3c-d7bb-4f6c-9938-e0e65d191433
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: ae8ce4c4b8090046baaa8306ea359471694b8bf2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33128655"
---
# <a name="how-to-iterate-over-a-user-defined-collection-with-for-each"></a>方法: for each を使用してユーサー定義のコレクションを反復処理する
マネージ コレクションであることのクラス、列挙子クラスまたはインターフェイスへのハンドルを返す非プライベート GetEnumerator 関数が必要です。  列挙子クラスには、非静的 MoveNext 関数と現在のプロパティの宣言を含める必要があります。  
  
## <a name="example"></a>例  
 シンプルなユーザーは、参照型のコレクションを定義します。  
  
```  
// for_each_user_defined_collections.cpp  
// compile with: /clr  
using namespace System;  
public interface struct IMyEnumerator {  
   bool MoveNext();  
   property Object^ Current {  
      Object^ get();  
   }  
   void Reset();  
};  
  
public ref struct MyArray {     
  
   MyArray( array<int>^ d ) {  
      data = d;  
   }  
  
   ref struct enumerator : IMyEnumerator {  
      enumerator( MyArray^ myArr ) {  
         colInst = myArr;  
         currentIndex = -1;  
      }  
  
      virtual bool MoveNext() {  
         if( currentIndex < colInst->data->Length - 1 ) {  
            currentIndex++;  
            return true;  
         }  
         return false;  
      }  
  
      property Object^ Current {  
         virtual Object^ get() {  
            return colInst->data[currentIndex];  
         }  
      };  
  
      virtual void Reset() {}  
      ~enumerator() {}  
  
      MyArray^ colInst;  
      int currentIndex;  
   };  
  
   array<int>^ data;  
  
   IMyEnumerator^ GetEnumerator() {  
      return gcnew enumerator(this);  
   }  
};  
  
int main() {  
   int retval = 0;  
  
   MyArray^ col = gcnew MyArray( gcnew array<int>{10, 20, 30 } );  
  
   for each ( Object^ c in col )  
      retval += (int)c;  
  
   retval -= 10 + 20 + 30;  
  
   for each ( int c in gcnew MyArray( gcnew array<int>{10, 20, 30 } ) )  
      retval += c;  
  
   retval -= 10 + 20 + 30;  
  
   Console::WriteLine("Return Code: {0}", retval );  
   return retval;  
}  
```  
  
```Output  
Return Code: 0  
```  
  
## <a name="see-also"></a>関連項目  
 [for each、in](../dotnet/for-each-in.md)