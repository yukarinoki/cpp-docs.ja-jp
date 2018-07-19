---
title: コンパイラ エラー C2708 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2708
dev_langs:
- C++
helpviewer_keywords:
- C2708
ms.assetid: d52d3088-1141-42f4-829c-74755a7fcc3a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d30b2e5c1856a604ae314316cd71d6acc00a7c74
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33234761"
---
# <a name="compiler-error-c2708"></a>コンパイラ エラー C2708
'identifier': 実引数の長さ (バイト単位) は、前の呼び出しまたは参照によって異なります。  
  
 A [_ _stdcall](../../cpp/stdcall.md)関数のプロトタイプで前にする必要があります。 それ以外の場合、コンパイラが関数にプロトタイプとして最初の呼び出しを解釈し、コンパイラと一致しない呼び出しが発生すると、このエラーが発生します。  
  
 修正は、このエラーは、関数プロトタイプを追加します。