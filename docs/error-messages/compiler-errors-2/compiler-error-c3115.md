---
title: コンパイラ エラー C3115 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3115
dev_langs:
- C++
helpviewer_keywords:
- C3115
ms.assetid: 51726145-9782-4ec9-84b9-286f366d9cbd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a8a324ede696e0af93b857e9605ad7c4b2aa8b73
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33251233"
---
# <a name="compiler-error-c3115"></a>コンパイラ エラー C3115
'attribute': 'construct' のこの属性は許可されていません  
  
 属性は、意図していないコンストラクトに適用されました。  参照してください[属性を使用して](../../windows/attributes-by-usage.md)詳細についてはします。  
  
## <a name="example"></a>例  
 次の例では、C3115 を生成します。  
  
```  
// C3115.cpp  
// compile with: /c  
#include <unknwn.h>  
[module(name="xx")];  
  
[object, helpstringdll(xx.dll), uuid("00000000-0000-0000-0000-000000000001")]   // C3115  
// try the following line instead  
// [object, uuid("00000000-0000-0000-0000-000000000001")]  
__interface IMyI {  
   HRESULT xx();  
};  
```