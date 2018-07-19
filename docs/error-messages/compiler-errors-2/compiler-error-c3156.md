---
title: コンパイラ エラー C3156 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3156
dev_langs:
- C++
helpviewer_keywords:
- C3156
ms.assetid: 1876da78-b94e-4af7-9795-28f72b209b3e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9557043bac056435dd53b210359e7bb72b29b6d7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33248230"
---
# <a name="compiler-error-c3156"></a>コンパイラ エラー C3156
'class' : マネージ型または WinRT 型のローカル定義を持つことができません  
  
 関数に、マネージ型または WinRT 型のクラス、構造体、インターフェイスの定義 (宣言) を含めることはできません。  
  
## <a name="example"></a>例  
 次の例では C3156 が生成されます。  
  
```  
// C3156.cpp  
// compile with: /clr /c  
void f() {  
   ref class X {};   // C3156  
   ref class Y;   // C3156  
}  
```  
