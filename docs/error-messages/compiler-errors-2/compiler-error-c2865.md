---
description: 詳細については、「コンパイラエラー C2865」を参照してください。
title: コンパイラ エラー C2865
ms.date: 11/04/2016
f1_keywords:
- C2865
helpviewer_keywords:
- C2865
ms.assetid: 973eb6a0-c99a-4d25-b3e5-fe0539794d77
ms.openlocfilehash: 0c57fdb120eb147b3877cc834e142ab92f147aaa
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97220748"
---
# <a name="compiler-error-c2865"></a>コンパイラ エラー C2865

' function ': handle_or_pointer の比較が正しくありません

[クラス、構造体](../../extensions/classes-and-structs-cpp-component-extensions.md)、またはマネージ参照型への参照は、等しいかどうかを比較して、同じオブジェクト (= =) を参照しているか、別のオブジェクト (! =) を参照しているかを調べることができます。

.NET ランタイムはマネージオブジェクトをいつでも移動し、テストの結果を変更することがあるため、順序を比較することはできません。
