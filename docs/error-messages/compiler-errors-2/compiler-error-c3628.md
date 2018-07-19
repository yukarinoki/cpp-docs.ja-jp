---
title: コンパイラ エラー C3628 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3628
dev_langs:
- C++
helpviewer_keywords:
- C3628
ms.assetid: 0ff5a4a4-fcc9-47a0-a4d8-8af9cf2815f6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5210a9bb91b86c63f0cebabce8901c9af50ae896
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33266416"
---
# <a name="compiler-error-c3628"></a>コンパイラ エラー C3628
'base class': マネージ配列または WinRTclasses はパブリック継承のみをサポート  
  
マネージまたは WinRT の使用を試みましたクラスの[プライベート](../../cpp/private-cpp.md)または[保護](../../cpp/protected-cpp.md)基本クラスです。 マネージ配列または WinRT クラスを持つ基本クラスとしてのみ使用できます[パブリック](../../cpp/public-cpp.md)アクセスします。  
  
次の例は C3628 を生成し、その修正方法を示しています。  
  
```  
// C3628a.cpp  
// compile with: /clr  
ref class B {  
};  
  
ref class D : private B {   // C3628  
  
// The following line resolves the error.  
// ref class D : public B {  
};  
  
int main() {  
}  
```  
