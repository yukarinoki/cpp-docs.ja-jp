---
description: 詳細については、「コンパイラエラー C2708」を参照してください。
title: コンパイラエラー C2708
ms.date: 11/04/2016
f1_keywords:
- C2708
helpviewer_keywords:
- C2708
ms.assetid: d52d3088-1141-42f4-829c-74755a7fcc3a
ms.openlocfilehash: c965375c92c98a58a0fb6d0d51b3358e6b5798b5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97320871"
---
# <a name="compiler-error-c2708"></a>コンパイラエラー C2708

' identifier ': 実際のパラメーターのバイト数が前回の呼び出しまたは参照と異なっています

[__Stdcall](../../cpp/stdcall.md)関数の前にはプロトタイプを指定しなければなりません。 それ以外の場合、コンパイラは関数の最初の呼び出しをプロトタイプとして解釈します。このエラーは、コンパイラが一致しない呼び出しを検出した場合に発生します。

このエラーを修正するには、関数プロトタイプを追加します。
