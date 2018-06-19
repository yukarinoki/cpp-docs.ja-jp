---
title: '方法: ユーザー インタラクティブな状態を確認する (C + + CLI) |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Visual C++, user interactive state
- user interactive state
ms.assetid: 9f52323e-38b8-4a41-9b1d-052012ad839b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 4649a6e7ce4833b55f38e636b87bb53f646e85cd
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33127306"
---
# <a name="how-to-determine-the-user-interactive-state-ccli"></a>方法: ユーザー インタラクティブな状態を確認する (C++/CLI)
次のコード例では、コードがユーザー対話型のコンテキストで実行されているかどうかを確認する方法を示します。 場合<xref:System.Environment.UserInteractive%2A>が false の場合、サービスのプロセスとして実行しているコードまたはから Web アプリケーションでは、内部場合必要がありますいないしようとするユーザーと対話します。  
  
## <a name="example"></a>例  
  
```  
// user_interactive.cpp  
// compile with: /clr  
using namespace System;  
  
int main()   
{  
   if ( Environment::UserInteractive )  
      Console::WriteLine("User interactive");  
   else  
      Console::WriteLine("Noninteractive");  
   return 0;  
}  
```  
  
## <a name="see-also"></a>関連項目  
 [Windows の操作 (C + + CLI)](../dotnet/windows-operations-cpp-cli.md)   
 [C++/CLI (Visual C++) による .NET プログラミング](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)