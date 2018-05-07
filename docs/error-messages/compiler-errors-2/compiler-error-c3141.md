---
title: コンパイラ エラー C3141 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3141
dev_langs:
- C++
helpviewer_keywords:
- C3141
ms.assetid: b4fd65c3-50cc-46cd-8de0-6a6d24cb9cda
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a394fb06fce8f482f42271052a3cf97b3711eaf2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3141"></a>コンパイラ エラー C3141
'interface_name': インターフェイスはパブリック継承のみをサポート  
  
 定義されているインターフェイス、[インターフェイス (または _ _interface)](../../cpp/interface.md)キーワードはパブリック継承のみをサポートします。  
  
 次の例では、C3141 が生成されます。  
  
```  
// C3141.cpp  
__interface IBase {};  
__interface IDerived1 : protected IBase {};  // C3141  
__interface IDerived2 : private IBase {};    // C3141  
```