---
title: コンパイラの警告 (レベル 1) C4729 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4729
dev_langs:
- C++
helpviewer_keywords:
- C4729
ms.assetid: 36a0151f-f258-48d9-9444-ae6d41ff70a4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7d1f5b4fe452937ce74e56886a5214ff92f44af7
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46096081"
---
# <a name="compiler-warning-level-1-c4729"></a>コンパイラの警告 (レベル 1) C4729

フロー グラフ ベースの警告の関数が大きすぎます。

この警告が生成されるのは、関数が大きすぎてコンパイルできず、警告を生成する状況を確実にチェックできない場合です。 この警告は、 [/Od](../../build/reference/od-disable-debug.md) コンパイラ オプションを使用している場合にのみ生成されます。

この警告を解決するには、関数を小さい関数に分割します。