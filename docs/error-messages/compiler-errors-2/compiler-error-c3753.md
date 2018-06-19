---
title: コンパイラ エラー C3753 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3753
dev_langs:
- C++
helpviewer_keywords:
- C3753
ms.assetid: a5b99e28-796c-4107-a673-97c2ae3bb2b9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b0d9cb2db2729e5ccb1787e2505fdf0aed1f7a12
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33271961"
---
# <a name="compiler-error-c3753"></a>コンパイラ エラー C3753
ジェネリック プロパティは使用できません。  
  
 ジェネリック パラメーター リストは、マネージ クラス、構造体、または関数でのみ使用できます。  
  
 詳細については、次を参照してください。[ジェネリック](../../windows/generics-cpp-component-extensions.md)と[プロパティ](../../windows/property-cpp-component-extensions.md)です。  
  
## <a name="example"></a>例  
 次の例では、C3753 を生成します。  
  
```  
// C3753.cpp  
// compile with: /clr /c  
ref struct A {  
   generic <typename T>  
   property int i;   // C3753 error  
};  
```