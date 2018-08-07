---
title: '方法: 内部ポインターとネイティブ ポインターと関数をオーバー ロード (C +/cli CLI) |Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- Functions with interior and native pointers, overloading
ms.assetid: d70df625-4aad-457c-84f5-70a0a290cc1f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 2fb1025238dc5cf5b186830d0bea3b896b7391ff
ms.sourcegitcommit: d5d6bb9945c3550b8e8864b22b3a565de3691fde
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2018
ms.locfileid: "39569961"
---
# <a name="how-to-overload-functions-with-interior-pointers-and-native-pointers-ccli"></a>方法: 内部ポインターとネイティブ ポインターを使用して関数をオーバーロードする (C++/CLI)
パラメーターの型は、内部ポインター、またはネイティブ ポインターかどうかに応じて関数をオーバー ロードできます。  
  
> [!IMPORTANT]
>  この言語機能がサポートされている、`/clr`コンパイラ オプションがなく、`/ZW`コンパイラ オプション。  
  
## <a name="example"></a>例  
  
### <a name="code"></a>コード  
  
```cpp  
// interior_ptr_overload.cpp  
// compile with: /clr  
using namespace System;  
  
// C++ class  
struct S {  
   int i;  
};  
  
// managed class  
ref struct G {  
   int i;  
};  
  
// can update unmanaged storage  
void f( int* pi ) {  
   *pi = 10;  
   Console::WriteLine("in f( int* pi )");  
}  
  
// can update managed storage  
void f( interior_ptr<int> pi ) {  
   *pi = 10;   
   Console::WriteLine("in f( interior_ptr<int> pi )");  
}  
  
int main() {  
   S *pS = new S;   // C++ heap  
   G ^pG = gcnew G;   // common language runtime heap  
   f( &pS->i );  
   f( &pG->i );  
};  
```  
  
### <a name="output"></a>出力  
  
```Output 
in f( int* pi )  
in f( interior_ptr<int> pi )  
```  
  
## <a name="see-also"></a>関連項目  
 [interior_ptr (C++/CLI)](../windows/interior-ptr-cpp-cli.md)