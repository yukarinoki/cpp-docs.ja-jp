---
title: コンパイラの警告 (レベル 4) C4611
ms.date: 11/04/2016
f1_keywords:
- C4611
helpviewer_keywords:
- C4611
ms.assetid: bd90d0a6-75f9-4e97-968d-dda6773e9fd8
ms.openlocfilehash: 7de4cdf0eacb1b9848a4350f1d223da1fd47d1fc
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80198303"
---
# <a name="compiler-warning-level-4-c4611"></a>コンパイラの警告 (レベル 4) C4611

' function ' とC++オブジェクトの破棄の間の相互作用は、移植不可です

一部のプラットフォームでは、 **catch**を含む関数はC++ 、スコープ外の場合に破棄のオブジェクトセマンティクスをサポートしていない可能性があります。

予期しない動作を回避するには、コンストラクターとデストラクターを持つ関数での**catch**の使用を避けてください。

この警告は1回のみ発行されます。[プラグマの警告](../../preprocessor/warning.md)を参照してください。
