---
title: コンパイラ エラー C3859 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3859
dev_langs:
- C++
helpviewer_keywords:
- C3859
ms.assetid: 40e93b25-4393-4467-90de-035434a665c7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d2f8c51f25c09881e10e980276fc2035a6a70aed
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33272306"
---
# <a name="compiler-error-c3859"></a>コンパイラ エラー C3859
PCH の仮想メモリの範囲が超えています。'-Zmvalue' 以上のコマンド ライン オプションで再コンパイルしてください。  
  
 プリコンパイル済みヘッダーが、コンパイラが挿入しようとしているデータの量に対して小さすぎます。 使用して、 **/Zm**コンパイラ フラグをプリコンパイル済みヘッダー ファイル用のより大きい値を指定します。 詳細については、次を参照してください。 [/Zm (指定プリコンパイル済みヘッダーのメモリ割り当て制限)](../../build/reference/zm-specify-precompiled-header-memory-allocation-limit.md)です。