---
title: コンパイラ エラー C3293 |Microsoft ドキュメント
ms.custom: ''
ms.date: 07/21/2017
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3293
dev_langs:
- C++
helpviewer_keywords:
- C3293
ms.assetid: b772cf98-52e0-4e24-be23-1f5d87d999ac
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b195a91825b0f20445b29e330f67810329584db7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3293"></a>コンパイラ エラー C3293
'accessor': クラス'type' の既定のプロパティ (インデクサー) にアクセスするには 'default' を使用してください  
  
 インデックス付きプロパティへのアクセスが正しくありません。  参照してください[する方法: プロパティを使用して C + + CLI](../../dotnet/how-to-use-properties-in-cpp-cli.md)詳細についてはします。  

 **2017 およびそれ以降の visual Studio**: Visual Studio 2015 およびそれ以前では、場合によっては、コンパイラは、既定のインデクサーとして既定のプロパティを正しく識別されません。 識別子 "default" を使用してプロパティにアクセスすることで、この問題を回避できました。 C++11 で default がキーワードとして導入された後は、この回避策自体が問題になりました。 そのため、Visual Studio 2017 では、この回避策を必要とするバグが修正され、クラスの既定のプロパティにアクセスするために "default" が使用された場合は、コンパイラがエラーを発生させるようになりました。
  
## <a name="example"></a>例  
 次の例では、Visual Studio 2015 以前のバージョンでは C3293 が生成されます。  
  
```  
// C3293.cpp  
// compile with: /clr /c  
using namespace System;  
ref class IndexerClass {  
public:  
   // default indexer  
   property int default[int] {  
      int get(int index) { return 0; }  
      void set(int index, int value) {}  
   }  
};  
  
int main() {  
   IndexerClass ^ ic = gcnew IndexerClass;  
   ic->Item[0] = 21;   // C3293 in VS2015 OK in VS2017
   ic->default[0] = 21;   // OK in VS2015 and earlier
  
   String ^s = "Hello";  
   wchar_t wc = s->Chars[0];   // C3293 in VS2015 OK in VS2017
   wchar_t wc2 = s->default[0];   // OK in VS2015 and earlier  
   Console::WriteLine(wc2);  
}  
```