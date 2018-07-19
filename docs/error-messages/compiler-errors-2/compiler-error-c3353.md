---
title: コンパイラ エラー C3353 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3353
dev_langs:
- C++
helpviewer_keywords:
- C3353
ms.assetid: 5699c04b-d504-46ce-bf71-c200318fed71
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 47c9d1dd8c21e56613b9da00fc2bf4f7fbeafcca
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33253906"
---
# <a name="compiler-error-c3353"></a>コンパイラ エラー C3353
'delegate': デリゲートはマネージ型または WinRT 型のグローバル関数またはメンバー関数からのみ作成できます  
  
 宣言されたデリゲートを[委任](../../windows/delegate-cpp-component-extensions.md)キーワードでは、グローバル スコープでのみ宣言できます。  
  
 次の例では C3353 が生成されます。  
  
```  
// C3353.cpp  
// compile with: /clr  
delegate int f;   // C3353  
```