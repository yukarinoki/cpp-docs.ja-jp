---
title: '方法: 現在のユーザー名を取得 (C + + CLI) |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- current user names
- user names, retrieving
- UserName string
ms.assetid: 91679571-d029-41f5-b657-1460c81c608a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 48b48b2d6ad84a85ca100c45a87f5d5037de684f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33127823"
---
# <a name="how-to-retrieve-the-current-username-ccli"></a>方法: 現在のユーザー名を取得する (C++/CLI)
次のコード例では、現在のユーザー名 (Windows にログオンしたユーザーの名前) の取得を示します。 格納されて、名前、<xref:System.Environment.UserName%2A>で定義されている文字列を<xref:System.Environment>名前空間。  
  
## <a name="example"></a>例  
  
```  
// username.cpp  
// compile with: /clr  
using namespace System;  
  
int main()   
{  
   Console::WriteLine("\nCurrent user: {0}", Environment::UserName);  
   return 0;  
}  
```  
  
## <a name="see-also"></a>関連項目  
 [Windows の操作 (C + + CLI)](../dotnet/windows-operations-cpp-cli.md)   
 [C++/CLI (Visual C++) による .NET プログラミング](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)