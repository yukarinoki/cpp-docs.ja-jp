---
description: 詳細については、「コンパイラエラー C2218」を参照してください。
title: コンパイラ エラー C2218
ms.date: 11/04/2016
f1_keywords:
- C2218
helpviewer_keywords:
- C2218
ms.assetid: b0f55da4-8edb-4b45-b298-1a091981bd7b
ms.openlocfilehash: d2761bb822c5a1055974e4a0bcd6011e7f451821
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97245526"
---
# <a name="compiler-error-c2218"></a>コンパイラ エラー C2218

> '__vectorcall' と '/arch:IA32' は同時に使用できません

**`__vectorcall`** 呼び出し規則は、ストリーミング SIMD 拡張命令 2 (SSE2) 以上を含む x86 および x64 プロセッサのネイティブコードでのみサポートされています。 詳細については、「[`__vectorcall`](../../cpp/vectorcall.md)」を参照してください。

このエラーを修正するには、SSE2、AVX、または AVX2 をターゲットにするようにコンパイラ オプションを変更します。 詳細については、 [`/arch` (x86)](../../build/reference/arch-x86.md) を参照してください。
