---
title: '方法: クリップボードのテキストを格納 (C + + CLI) |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- text, storing in Clipboard
- Clipboard, storing text
ms.assetid: 9996023f-b700-47ad-8ad9-1ba201eaa5a6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 9ac33eb31dbda97d3c695847344cd857d2e77675
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33138520"
---
# <a name="how-to-store-text-in-the-clipboard-ccli"></a>方法: クリップボード内にテキストを格納する (C++/CLI)
次のコード例では、<xref:System.Windows.Forms.Clipboard>で定義されているオブジェクト、<xref:System.Windows.Forms>文字列を格納する名前空間。 このオブジェクトは、次の 2 つのメンバー関数を提供します。<xref:System.Windows.Forms.Clipboard.SetDataObject%2A>と<xref:System.Windows.Forms.Clipboard.GetDataObject%2A>です。 派生した任意のオブジェクトを送信することによってデータがクリップボードに格納されている<xref:System.Object>に<xref:System.Windows.Forms.Clipboard.SetDataObject%2A>です。  
  
## <a name="example"></a>例  
  
```  
// store_clipboard.cpp  
// compile with: /clr  
#using <System.dll>  
#using <System.Drawing.dll>  
#using <System.Windows.Forms.dll>  
  
using namespace System;  
using namespace System::Windows::Forms;  
  
[STAThread] int main()  
{  
   String^ str = "This text is copied into the Clipboard.";  
  
   // Use 'true' as the second argument if  
   // the data is to remain in the clipboard  
   // after the program terminates.  
   Clipboard::SetDataObject(str, true);  
  
   Console::WriteLine("Added text to the Clipboard.");  
  
   return 0;  
}  
```  
  
## <a name="see-also"></a>関連項目  
 [方法: クリップボードからテキストを取得 (C + + CLI)](../dotnet/how-to-retrieve-text-from-the-clipboard-cpp-cli.md)   
 [Windows の操作 (C + + CLI)](../dotnet/windows-operations-cpp-cli.md)   
 [C++/CLI (Visual C++) による .NET プログラミング](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)