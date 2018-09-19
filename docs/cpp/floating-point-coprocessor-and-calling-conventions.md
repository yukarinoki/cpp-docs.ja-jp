---
title: 浮動小数点コプロセッサと呼び出し規約 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- floating-point numbers [C++]
- floating-point coprocessor
ms.assetid: 3cc6615a-b308-4cf7-9570-83e192a832b3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e9f45f73e3cb1910bfc604c8a0fde871cef973a9
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46075957"
---
# <a name="floating-point-coprocessor-and-calling-conventions"></a>浮動小数点コプロセッサと呼び出し規則

を作成しているアセンブリ ルーチンが浮動小数点コプロセッサ場合、浮動小数点を保持する必要がある制御ワードをポイントし、返す場合を除き、コプロセッサ スタックをクリーンアップする**float**または**二重**値 (これは、関数は、ST(0)) で返す必要があります。

## <a name="see-also"></a>関連項目

[呼び出し規約](../cpp/calling-conventions.md)