---
description: 詳細については、「コンパイラエラー C2919」を参照してください。
title: コンパイラ エラー C2919
ms.date: 11/04/2016
f1_keywords:
- C2919
helpviewer_keywords:
- C2919
ms.assetid: 140a6db9-eb48-4c5e-84a7-a09d2653605b
ms.openlocfilehash: 0e6498961fc5000897bcd9815c3cd3a6f90ecdfb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97270343"
---
# <a name="compiler-error-c2919"></a>コンパイラ エラー C2919

'type': WinRT 型の発行サーフェスでは演算子は使用できません

Windows ランタイムの型システムでは、型の発行サーフェスで演算子メンバー関数をサポートしていません。 これは、すべての言語で演算子メンバー関数を使用できるとは限らないためです。 同じクラスまたはコンパイル ユニット内に、C++ コードから呼び出されるプライベートまたは内部の演算子メンバー関数を作成できます。

この問題を解決するには、演算子メンバー関数をパブリック インターフェイスから削除するか、名前付きのメンバー関数に変更します。 たとえば、`operator==` の代わりに、メンバー関数に `Equals` という名前を付けます。
