---
description: '詳細情報: コンパイラの警告 (レベル 4) C4611'
title: コンパイラの警告 (レベル 4) C4611
ms.date: 11/04/2016
f1_keywords:
- C4611
helpviewer_keywords:
- C4611
ms.assetid: bd90d0a6-75f9-4e97-968d-dda6773e9fd8
ms.openlocfilehash: df53392b2d56b9afb1ab0cbcb2fc7b6267d5f00f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97168268"
---
# <a name="compiler-warning-level-4-c4611"></a>コンパイラの警告 (レベル 4) C4611

' function ' と C++ オブジェクトの破棄の間の相互作用は、移植不可です

一部のプラットフォームでは、が含まれている関数は、スコープ外の **`catch`** 場合に、デストラクターの C++ オブジェクトセマンティクスをサポートしていない可能性があります。

予期しない動作を避けるため、 **`catch`** コンストラクターとデストラクターを持つ関数ではを使用しないでください。

この警告は1回のみ発行されます。 [プラグマの警告](../../preprocessor/warning.md)を参照してください。
