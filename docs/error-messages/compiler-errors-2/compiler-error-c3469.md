---
title: コンパイラ エラー C3469 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3469
dev_langs:
- C++
helpviewer_keywords:
- C3469
ms.assetid: e23b0e5c-c704-4e67-a868-bf02c2055d85
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4f9ddd172678ea9895bb5daa32e7a325ed8eaa01
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33256975"
---
# <a name="compiler-error-c3469"></a>コンパイラ エラー C3469
'type': ジェネリック クラスを転送することはできません  
  
 ジェネリック クラスでは型の転送を使用できません。  
  
 詳細については、次を参照してください。 [Type Forwarding (C + + CLI)](../../windows/type-forwarding-cpp-cli.md)です。  
  
## <a name="example"></a>例  
 コンポーネントを作成する例を次に示します。  
  
```  
// C3469.cpp  
// compile with: /clr /LD  
generic<typename T>  
public ref class GR {};  
  
public ref class GR2 {};  
```  
  
## <a name="example"></a>例  
 次の例では C3466 が生成されます。  
  
```  
// C3469_b.cpp  
// compile with: /clr /c  
#using "C3469.dll"  
[assembly:TypeForwardedTo(GR::typeid)];   // C3469  
[assembly:TypeForwardedTo(GR2::typeid)];   // OK  
```