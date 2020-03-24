---
title: コンパイラエラー C2708
ms.date: 11/04/2016
f1_keywords:
- C2708
helpviewer_keywords:
- C2708
ms.assetid: d52d3088-1141-42f4-829c-74755a7fcc3a
ms.openlocfilehash: a1d3379a0da42c5aabd38cffbf6f6a3f340ef3b9
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80202372"
---
# <a name="compiler-error-c2708"></a>コンパイラエラー C2708

' identifier ': 実際のパラメーターのバイト数が前回の呼び出しまたは参照と異なっています

[__Stdcall](../../cpp/stdcall.md)関数の前にはプロトタイプを指定しなければなりません。 それ以外の場合、コンパイラは関数の最初の呼び出しをプロトタイプとして解釈します。このエラーは、コンパイラが一致しない呼び出しを検出した場合に発生します。

このエラーを修正するには、関数プロトタイプを追加します。
