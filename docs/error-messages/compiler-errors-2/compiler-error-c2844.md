---
title: コンパイラ エラー C2844 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2844
dev_langs:
- C++
helpviewer_keywords:
- C2844
ms.assetid: dcaf4cd2-21b0-4280-ae42-0a706c524d83
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4a45e4a94e3d474be670f822d56a7c080f25693c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2844"></a>コンパイラ エラー C2844
'member': インターフェイス 'interface' のメンバーであることはできません  
  
 [インターフェイス クラス](../../windows/interface-class-cpp-component-extensions.md)プロパティでもある場合を除き、データ メンバーを含めることはできません。  
  
 インターフェイス内でプロパティまたはメンバー関数以外のものは許可されません。 さらに、コンス トラクター、デストラクター、および演算子は使用できません。  
  
 次の例では、C2844 が生成されます。  
  
```  
// C2844a.cpp  
// compile with: /clr /c  
public interface class IFace {  
   int i;   // C2844  
   // try the following line instead  
   // property int Size;  
};  
```  
