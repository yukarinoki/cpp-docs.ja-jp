---
title: コンパイラの警告 (レベル 4) C4337 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4337
dev_langs:
- C++
helpviewer_keywords:
- C4337
ms.assetid: 70bc72d9-aac5-45cd-abd3-ebe42a05897b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 75e77187f871373957ab68108a7fa14c0751a92a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33295156"
---
# <a name="compiler-warning-level-4-c4337"></a>コンパイラの警告 (レベル 4) C4337
クロスレファレンスしたタイプ ライブラリ 'typelib1' 'typelib2' では自動的にインポートしています  
  
 Auto_search 属性[#import ディレクティブ](../../preprocessor/hash-import-directive-cpp.md)を暗黙的にインポートするタイプ ライブラリの原因となった。  
  
 (Midl.exe でコンパイルされた) 次の 2 つのファイルから作成されたディスクに指定された 2 つのタイプ ライブラリ:  
  
```  
// C4337a.idl  
[  
  uuid(F87070BA-C6D9-405C-A8E4-8CD9CA25C12B)  
]  
library C4337aLib  
{  
   [uuid(F87070BA-C6D9-405C-A8E4-8CD9CA25C12C)]  
   enum E_C4337a  
   {  
      one = 0,  
      two = 1,  
      three = 2  
    };  
};  
```  
  
 2 番目 .idl ファイル  
  
```  
// C4337b.idl  
[  
   uuid(F87070BA-C6D9-405C-A8E4-8CD9CA25C12D)  
]  
  
library C4337bLib  
{  
   importlib("c4337a.tlb");  
  
   [uuid(F87070BA-C6D9-405C-A8E4-8CD9CA25C12E)]  
   struct S_C4337b  
   {  
      enum E_C4337a e;  
   };  
};  
```  
  
 次の例では、C4337 が生成されます。  
  
```  
// C4337.cpp  
// compile with: /W4 /LD  
#import "c4337b.tlb" auto_search   // C4337  
// explicitly #import all type libraries to resolve  
// #import "C4337a.tlb"  
// #import "C4337b.tlb"  
```