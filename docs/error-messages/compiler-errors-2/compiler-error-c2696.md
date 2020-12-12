---
description: 詳細については、「コンパイラエラー C2696」を参照してください。
title: コンパイラエラー C2696
ms.date: 11/04/2016
f1_keywords:
- C2696
helpviewer_keywords:
- C2696
ms.assetid: 6c6eb7df-1230-4346-9a73-abf14c20785d
ms.openlocfilehash: 2d4a798258ba6f9bb467c4da32e75860b96874e1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97326616"
---
# <a name="compiler-error-c2696"></a>コンパイラエラー C2696

マネージド型 ' type ' の一時オブジェクトを作成することはできません

アンマネージプログラムでへの参照を行う **`const`** と、コンパイラがコンストラクターを呼び出し、スタックに一時オブジェクトを作成します。 ただし、マネージクラスをスタックに作成することはできません。

C2696 は、互換性のために残されているコンパイラオプション **/clr: oldSyntax** を使用してのみ到達可能です。
