---
title: '方法: 正規表現を使用して文字列の解析 (C + + CLI) |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- parsing strings [C++]
- examples [C++], strings
- regular expressions [C++], parsing strings
- strings [C++], parsing
ms.assetid: 5b0c7ca3-9bba-4389-a45c-6d373cff91b0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 5940a59d7e9b4e68f289848523710594621e73d4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-parse-strings-using-regular-expressions-ccli"></a>方法: 正規表現を使用して文字列を解析する (C++/CLI)
<xref:System.Text.RegularExpressions.Regex> 名前空間の <xref:System.Text.RegularExpressions?displayProperty=fullName> クラスを使用して単純な文字列を解析する方法を次のコード例に示します。 複数のワード デリニエイタの型を含む文字列が構成されます。 次に、<xref:System.Text.RegularExpressions.Regex> クラスを <xref:System.Text.RegularExpressions.Match> クラスと共に使用して文字列が解析されます。 さらに、センテンス内の各単語を個別に表示します。  
  
## <a name="example"></a>例  
  
```  
// regex_parse.cpp  
// compile with: /clr  
#using <system.dll>  
  
using namespace System;  
using namespace System::Text::RegularExpressions;  
  
int main( )  
{  
   int words = 0;  
   String^ pattern = "[a-zA-Z]*";  
   Console::WriteLine( "pattern : '{0}'", pattern );  
   Regex^ regex = gcnew Regex( pattern );  
  
   String^ line = "one\ttwo three:four,five six  seven";     
   Console::WriteLine( "text : '{0}'", line );  
   for( Match^ match = regex->Match( line );   
        match->Success; match = match->NextMatch( ) )   
   {  
      if( match->Value->Length > 0 )  
      {  
         words++;  
         Console::WriteLine( "{0}", match->Value );  
      }  
   }  
   Console::WriteLine( "Number of Words : {0}", words );  
  
   return 0;  
}  
```  
  
## <a name="see-also"></a>関連項目  
 [.NET Framework 正規表現](/dotnet/standard/base-types/regular-expressions)   
 [C++/CLI (Visual C++) による .NET プログラミング](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)