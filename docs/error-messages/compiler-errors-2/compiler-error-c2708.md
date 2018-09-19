---
title: コンパイラ エラー C2708 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2708
dev_langs:
- C++
helpviewer_keywords:
- C2708
ms.assetid: d52d3088-1141-42f4-829c-74755a7fcc3a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c0accd68881cccad5e34530a6c157a4e8179b283
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46111096"
---
# <a name="compiler-error-c2708"></a>コンパイラ エラー C2708

'identifier': 実パラメーターの長さ (バイト単位) は、前の呼び出しまたは参照によって異なります。

A [_ _stdcall](../../cpp/stdcall.md)関数プロトタイプの前が必要です。 それ以外の場合、コンパイラは、最初のプロトタイプとして関数呼び出しを解釈し、コンパイラと一致しない呼び出しを検出すると、このエラーが発生します。

修正するのには、このエラーは、関数プロトタイプを追加します。