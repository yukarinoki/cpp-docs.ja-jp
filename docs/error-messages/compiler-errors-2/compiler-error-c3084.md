---
title: コンパイラ エラー C3084 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3084
dev_langs:
- C++
helpviewer_keywords:
- C3084
ms.assetid: 0362cb70-e24e-476f-a24d-8f5bb97c3afd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 959d2eb46d7a2c85cc25adf681c760fa1f8dc4fa
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3084"></a>コンパイラ エラー C3084
'function': ファイナライザーまたはデストラクターを 'keyword' にすることはできません。  
  
 ファイナライザーまたはデストラクターの宣言が正しくありません。  
  
 たとえば、デストラクターをシール済みとしてマークすることはできません。  デストラクターは派生型にアクセスできません。  詳細については、次を参照してください。[明示的なオーバーライド](../../windows/explicit-overrides-cpp-component-extensions.md)と[する方法のデストラクターおよびファイナライザー: を定義およびクラスと構造体を使用 (C + + CLI)](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers)です。  
  
## <a name="example"></a>例  
 次の例では C3084 が生成されます。  
  
```  
// C3084.cpp  
// compile with: /clr /c  
ref struct R {  
protected:  
   !R() sealed;   // C3084  
   !R() abstract;   // C3084  
   !R();  
};  
```