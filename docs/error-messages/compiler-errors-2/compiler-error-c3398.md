---
title: コンパイラ エラー C3398 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3398
dev_langs:
- C++
helpviewer_keywords:
- C3398
ms.assetid: 26f8c8a4-526f-415b-8047-155c5cd4f180
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b870479977bfb49ff39d5a15fe19fc700ed66b8e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33255832"
---
# <a name="compiler-error-c3398"></a>コンパイラ エラー C3398
'operator': 'function_signature' から 'function_pointer' に変換できません。 ソース式は関数シンボルでなければなりません  
  
 [/clr](../../cpp/clrcall.md) を使用してコンパイルするときに、 **__clrcall**呼び出し規則が指定されていないと、コンパイラは各関数に対して、ネイティブ エントリ ポイントとマネージ エントリ ポイントという 2 つのエントリ ポイント (アドレス) を生成します。  
  
 既定では、コンパイラはネイティブ エントリ ポイントを返しますが、場合によっては、マネージ エントリ ポイントが必要な場合があります (たとえば、 `__clrcall` 関数ポインターにアドレスを 割り当てる場合など)。 割り当てでコンパイラが確実にマネージ エントリ ポイントを選択するためには、右辺を関数シンボルにする必要があります。