---
title: コンパイラ エラー C3828 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3828
dev_langs:
- C++
helpviewer_keywords:
- C3828
ms.assetid: 8d9cee75-9504-4bc8-88b6-2413618a3f45
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: adb016c164923e1ac6008e6318e39f8ac8632113
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33267421"
---
# <a name="compiler-error-c3828"></a>コンパイラ エラー C3828
'object type': クラスまたは WinRTclasses 仮引数のマネージ インスタンスの作成中に許可されていません  
  
 マネージ型または Windows ランタイム型のオブジェクトを作成する場合は、演算子の配置形式を使用することはできません[ref new、gcnew](../../windows/ref-new-gcnew-cpp-component-extensions.md)または[新しい](../../cpp/new-operator-cpp.md)です。  
  
 次の例では、C3828 を生成し、その修正方法を示しています。  
  
```  
// C3828a.cpp  
// compile with: /clr  
ref struct M {  
};  
  
ref struct N {  
   static array<char>^ bytes = gcnew array<char>(256);  
};  
  
int main() {  
   M ^m1 = new (&N::bytes) M();   // C3828  
   // The following line fixes the error.  
   // M ^m1 = gcnew M();  
}  
```