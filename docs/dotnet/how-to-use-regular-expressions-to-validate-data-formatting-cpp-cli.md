---
title: 書式設定を検証する正規表現の使用 (C + + CLI) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- strings [C++], formatting
- data [C++], formatting
- regular expressions [C++], validating data formatting
ms.assetid: 225775c3-3efc-4734-bde2-1fdf73e3d397
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 59a553ac2d58f9304fce3961aa8212c33b26643a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33129617"
---
# <a name="how-to-use-regular-expressions-to-validate-data-formatting-ccli"></a>方法: 正規表現を使用してデータ書式設定を検証する (C++/CLI)
次のコード例では、文字列の書式設定を検証する正規表現の使用を示します。 次のコード例では、文字列は有効な電話番号を含める必要があります。 次のコード例は、文字列を使用して"\d{3}-\d{3}-\d{4}"の各フィールドが有効な電話番号を表すことを示すためにします。 文字列に"d"は、数字を示し、"d"の後の引数が存在する必要がある数字の数を示します。 ここでは、数はダッシュで区切られているために必要です。  
  
## <a name="example"></a>例  
  
```  
// regex_validate.cpp  
// compile with: /clr  
#using <System.dll>  
  
using namespace System;  
using namespace Text::RegularExpressions;  
  
int main()  
{  
   array<String^>^ number =   
   {  
      "123-456-7890",   
      "444-234-22450",   
      "690-203-6578",   
      "146-893-232",  
      "146-839-2322",  
      "4007-295-1111",   
      "407-295-1111",   
      "407-2-5555",   
   };  
  
   String^ regStr = "^\\d{3}-\\d{3}-\\d{4}$";  
  
   for ( int i = 0; i < number->Length; i++ )  
   {  
      Console::Write( "{0,14}", number[i] );  
  
      if ( Regex::IsMatch( number[i], regStr ) )  
         Console::WriteLine(" - valid");  
      else  
         Console::WriteLine(" - invalid");  
   }  
   return 0;  
}  
```  
  
## <a name="see-also"></a>関連項目  
 [.NET Framework 正規表現](/dotnet/standard/base-types/regular-expressions)   
 [C++/CLI (Visual C++) による .NET プログラミング](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)