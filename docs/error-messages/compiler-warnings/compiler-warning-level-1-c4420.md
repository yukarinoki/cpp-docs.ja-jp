---
description: '詳細情報: コンパイラの警告 (レベル 1) C4420'
title: コンパイラの警告 (レベル 1) C4420
ms.date: 11/04/2016
f1_keywords:
- C4420
helpviewer_keywords:
- C4420
ms.assetid: 44a37754-7ddd-4764-a5f7-d33e05c20091
ms.openlocfilehash: 2a92d7296bf5c38655182e5c0dd2c200d0ccf42d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97311072"
---
# <a name="compiler-warning-level-1-c4420"></a>コンパイラの警告 (レベル 1) C4420

' operator ': 演算子は使用できません。代わりに ' operator ' を使用します。実行時チェックが危害を受ける可能性があります

この警告は、 [/RTCv](../../build/reference/rtc-run-time-error-checks.md) (ベクターの新規/削除チェック) を使用する場合と、ベクター形式が見つからない場合に生成されます。 この場合、非ベクター形式が使用されます。

/RTCv が正しく機能するためには、 [](../../cpp/new-operator-cpp.md) / ベクター構文が使用されている場合、コンパイラは常に新しい[delete](../../cpp/delete-operator-cpp.md)の vector 形式を呼び出す必要があります。
