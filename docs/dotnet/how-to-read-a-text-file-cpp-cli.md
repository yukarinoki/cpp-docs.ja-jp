---
title: '方法: テキスト ファイルを読み取り (C + + CLI) |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- reading text files
- text files, reading
ms.assetid: 80551c01-d769-4b6d-8db7-fd53bde21b62
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: c350ea9cd8b71378d059a93ac80ca808d4f48790
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-read-a-text-file-ccli"></a>方法: テキスト ファイルを読み込む (C++/CLI)
<xref:System.IO.StreamReader> クラスを使用して、テキスト ファイルを一度に 1 行ずつ開いて読み取る方法を次の例に示します。このクラスは、<xref:System.IO?displayProperty=fullName> 名前空間で定義されています。 このクラスのインスタンスを使用してテキスト ファイルを開いてから、<xref:System.IO.StreamReader.ReadLine%2A?displayProperty=fullName> メソッドを使用して各行を取得します。  
  
 このコード例では、テキストが含まれる textfile.txt というファイルを読み取ります。 この種類のファイルについては、次を参照してください。[する方法: テキスト ファイルを書き込む (C + + CLI)](../dotnet/how-to-write-a-text-file-cpp-cli.md)です。  
  
## <a name="example"></a>例  
  
```  
// text_read.cpp  
// compile with: /clr  
#using<system.dll>  
using namespace System;  
using namespace System::IO;  
  
int main()  
{  
   String^ fileName = "textfile.txt";  
   try   
   {  
      Console::WriteLine("trying to open file {0}...", fileName);  
      StreamReader^ din = File::OpenText(fileName);  
  
      String^ str;  
      int count = 0;  
      while ((str = din->ReadLine()) != nullptr)   
      {  
         count++;  
         Console::WriteLine("line {0}: {1}", count, str );  
      }  
   }  
   catch (Exception^ e)  
   {  
      if (dynamic_cast<FileNotFoundException^>(e))  
         Console::WriteLine("file '{0}' not found", fileName);  
      else  
         Console::WriteLine("problem reading file '{0}'", fileName);  
   }  
  
   return 0;  
}  
```  
  
## <a name="see-also"></a>関連項目  
 [ファイルおよびストリーム入出力](http://msdn.microsoft.com/Library/4f4a33a9-66b7-4cd7-a285-4ad3e4276cd2)   
 [C++/CLI (Visual C++) による .NET プログラミング](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)