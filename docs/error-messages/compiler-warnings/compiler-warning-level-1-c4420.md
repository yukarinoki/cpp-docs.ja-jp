---
title: コンパイラの警告 (レベル 1) C4420
ms.date: 11/04/2016
f1_keywords:
- C4420
helpviewer_keywords:
- C4420
ms.assetid: 44a37754-7ddd-4764-a5f7-d33e05c20091
ms.openlocfilehash: 72ab87b34e07717112f5af1727a216b4f786ae0d
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80186791"
---
# <a name="compiler-warning-level-1-c4420"></a>コンパイラの警告 (レベル 1) C4420

' operator ': 演算子は使用できません。代わりに ' operator ' を使用します。実行時チェックが危害を受ける可能性があります

この警告は、 [/RTCv](../../build/reference/rtc-run-time-error-checks.md) (ベクターの新規/削除チェック) を使用する場合と、ベクター形式が見つからない場合に生成されます。 この場合、非ベクター形式が使用されます。

/RTCv が正しく機能するためには、vector 構文が使用されている場合、コンパイラは常に、vector 形式の[new](../../cpp/new-operator-cpp.md)/[delete](../../cpp/delete-operator-cpp.md)を呼び出す必要があります。
