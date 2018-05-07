---
title: '方法: シャット ダウンが開始されたかどうかを判断 (C + + CLI) |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- .NET Framework, shutdown
- shutdown
- termination
- applications [C++], shutdown
ms.assetid: a8d39731-dea8-4f0a-96b7-2a5de09b21d7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: bbcc2b1efa54808b25238bde4de3dcc21d2ba687
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-determine-if-shutdown-has-started-ccli"></a>方法: シャットダウンが開始されたかどうかを確認する (C++/CLI)
次のコード例では、アプリケーションまたは .NET Framework が終了して現在あるかどうかを確認する方法を示します。 これは、ため、シャット ダウン中、これらの構造がシステムによって完了し、確実に使用することはできません、.NET Framework での静的な要素にアクセスするため便利です。 チェックして、<xref:System.Environment.HasShutdownStarted%2A>プロパティ最初に、これらの要素にアクセスするいないと、潜在的な障害を回避できます。  
  
## <a name="example"></a>例  
  
```  
// check_shutdown.cpp  
// compile with: /clr  
using namespace System;  
int main()   
{  
   if (Environment::HasShutdownStarted)  
      Console::WriteLine("Shutting down.");  
   else  
      Console::WriteLine("Not shutting down.");  
   return 0;  
}  
```  
  
## <a name="see-also"></a>関連項目  
 [Windows の操作 (C + + CLI)](../dotnet/windows-operations-cpp-cli.md)   
 [C++/CLI (Visual C++) による .NET プログラミング](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)