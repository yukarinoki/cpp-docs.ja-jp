---
title: コンパイラ エラー C2696 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2696
dev_langs:
- C++
helpviewer_keywords:
- C2696
ms.assetid: 6c6eb7df-1230-4346-9a73-abf14c20785d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 65ccdd6d2c8c34c360811b80d5a93abe76f5ef8e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2696"></a>コンパイラ エラー C2696
マネージ型 'type' の一時オブジェクトを作成することはできません。  
  
参照`const`アンマネージ プログラム コンパイラ コンス トラクターを呼び出すし、スタック上に一時オブジェクトを作成することが原因です。 ただし、マネージ クラスは、スタックに作成されません。  
  
C2696 は古い形式のコンパイラ オプションを使用して到達のみ **/clr:oldSyntax**です。  
