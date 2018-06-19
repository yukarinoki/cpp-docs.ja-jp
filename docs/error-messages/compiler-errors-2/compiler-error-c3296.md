---
title: コンパイラ エラー C3296 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3296
dev_langs:
- C++
helpviewer_keywords:
- C3296
ms.assetid: fc4c9dcd-16cf-4eee-a1ac-c43e7c29e443
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 85b4f80a9f257fa5e5d9ed8701a6ee7cfdf68cfd
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33249968"
---
# <a name="compiler-error-c3296"></a>コンパイラ エラー C3296
'property': この名前のプロパティが既に存在します  
  
 コンパイラは同じ名前の 1 つ以上のプロパティを見つけました。 1 つの型の各プロパティには、一意の名前が必要です。  
  
 詳細については、「 [property](../../windows/property-cpp-component-extensions.md)」を参照してください。  
  
## <a name="example"></a>例  
 次の例では C3296 が生成されます。  
  
```  
// C3296.cpp  
// compile with: /clr /c  
using namespace System;  
  
ref class R {  
public:  
   property int MyProp[int] { int get(int); }  
  
   property String^ MyProp[int] { void set(int, String^); }   // C3296  
};  
```